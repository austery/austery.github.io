---
author: EO
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LQy2FTnwiLk
speaker: EO
tags:
  - on-device-ai
  - ai-agent
  - autonomous-agents
  - privacy
title: 深入端侧 AGI 初创公司：48小时探秘 AGI Inc 的设备端个人 AI 愿景
summary: 本期专访深入初创公司 AGI Inc，创始人 Div Garg 及核心团队阐述了其构建端侧个人 AI 智能体的愿景与工程挑战。团队分享了从 Stanford 创办首门 Transformer 课程到退学创业的过程，展示了通过手机屏幕截图与动作模型实现无缝跨 App 操作的 Demo，并探讨了端侧部署对隐私保护、复合错误率优化以及摆脱屏幕束缚的核心价值。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Div Garg
  - Steve
  - Naman
companies_orgs:
  - AGI Inc
  - Qualcomm
  - OpenAI
  - Anthropic
products_models:
  - DoorDash
  - Android
media_books: []
status: evergreen
---
### 愿景与端侧个人 AI 的定义

>> 大多数人对 AI 的体验仍然停留在聊天机器人阶段。未来的常态将是你直接对设备说话，它就会替你把事情办妥。想象一下类似《钢铁侠》里的贾维斯（Jarvis）。无论我身在何处，我都拥有一个属于我自己的 AI。这是我的个人 AI。而借助你们正在构建的东西，这在当下已经成为可能。我想要一份 Chipotle 的牛排肉卷、糙米饭、炒蔬菜、酸奶油和一些奶酪。食物送到了。我们可以拥有一支智能体大军，基本上能替你处理所有事情。全人类都能在同一个基准上实现平等。而我们希望让这一切发生。你将拥有一整套新形态的设备，比如智能可穿戴硬件。这绝对会引起超大范围的病毒式传播。没错。我们有一系列可以直接对着说话的类似吊坠的设备。请帮我冲一杯咖啡。我们还与高通等芯片公司展开了合作。你如何将那种演示变成真正的产品？产品。打造出产品，对。把它做得真实且出色。其余的一切都会随之而来。而这正是人们来找我们的原因，因为我们是唯一真正切实去解决这项挑战的人。这是一家类似于 996 节奏的公司。我基本上每天都是从早上 9:30 工作到晚上 9:30。如果你热爱自己在做的事，这就无所谓了。我从斯坦福大学的博士项目退学，拒绝了来自 OpenAI 的一份极高报价，全力投入构建 AGI。我们构建了自己的端侧模型，能够直接在你的手机上执行操作。因此，它能够为你掌控整个手机并使用任何应用程序。我认为这是我们当下能为全人类所做的最具影响力的事情。
<details><summary>Original English</summary>
>> Most people's experience of AI is still chatbots. 
The future is that you just talk to your device  
and it does things for you. Imagine something 
like Jarvis from Iron Man. Wherever I am,  
I have an AI that I own. It's my personal AI. 
And that's possible right now with like things  
you're building. I want a chipotle 
steak, brown rice, wok, sour cream,  
and some cheese. Food is here. We can have an army 
of agents that can basically go and do everything  
for you. The whole humanity gets equalized on 
the same basis. And we want to make that happen.  
You will have a whole suite of new devices, 
like smart variables. This is going to go mega  
viral. Yeah. We have a line of like pendants that 
you speak into. Brew me a coffee, please. We also  
partner with like uh chip companies like Qualcomm. 
How do you make that demo into a real product?  
Product. Make the product, yeah. Make it real and 
good. Everything follows from there. And that's  
what like people are coming to us for because 
we're the only ones who are actually really  
solving that challenge. This is like a 996 type of 
company. I end up doing like 9:30 to 9:30 pretty  
much every day. If you love what you're doing, 
it doesn't matter. I dropped out of my Stanford  
PhD and turned down a billion-dollar offer from 
OpenAI to build AGI. We built our own on-device  
models that can go and take actions on your phone. 
So, you can control your whole phone and use any  
app for you. I think this is the most impactful 
thing we can do for the whole humanity right now.
</details>

### 入职第一天与公司氛围

>> 正在签署我的合同。太棒了。是的。感受这里的活力。这是我在 AGI 的第一天。我叫 Shariq。今天是我入职培训的日子，我超级兴奋。在这之前，我一直在大量从事语音 AI 和语音大语言模型的相关工作。我们的实习生不用去拿咖啡。我们有能帮我们冲咖啡的智能体。打开咖啡链接。
<details><summary>Original English</summary>
>> Signing my contract. Yes. Yeah. Uh feel 
the energy. Uh it's my day one at AGI.  
Uh my name is Shariq. Today is going to be my 
onboarding and I'm super excited. Before this,  
uh I was working a lot with uh voice 
AI and voice LLMs. Our interns don't  
pick up coffee. We have agents that 
make us coffee. Open coffee link.
</details>

>> 然后在咖啡下方点击冲泡。
<details><summary>Original English</summary>
>> And click brew under coffee.
</details>

>> 他顺利完成入职了吗？你通过了我的测试。接下来是 Naman 和 Div 的环节，那完全是另一场测试了。两天前在 AGI Inc. 举办的派对或者联合办公活动上，我跟 Div 聊过。我向他询问了目前 AGI 领域存在的其他竞争对手的情况。我对他们三个人问了完全相同的问题，而我非常喜欢他们给出的答案。他们并不认为对方是狭隘意义上的竞争对手，因为大家都在以某种方式推动这个领域向前发展。竞争越多，你反而能把东西造得越好。我觉得作为创始人，如果能站在整个本地设备与语音体系如何演进的全局高度去思考，而不是只局限在自家产品本身的推进上，这是非常积极且健康的态度。我是 Div Garg，AGI Inc. 的创始人兼 CEO。我们正在打造世界上真正意义上的个人 AI，它将运行在你的手机以及任何其他设备上，包括智能眼镜和智能手表。我们构建了自己的端侧模型，能够在你的手机上直接执行操作。因此，它能够为你掌控整个手机并使用任何 App。眼下，我们在类似 AndroidWorld 等行业基准评测中实际上名列第一。
<details><summary>Original English</summary>
>> Is he successfully on board yet? You passed my 
test. Next is Num One and Div, that's a whole  
different test. So, I I talked to Div at the 
AGI Inc. party or the co-working session that  
they hosted a couple of days back. I kind of asked 
him about other competition that exists for AGI.  
I asked all three of them the exact same question 
and I love their answer to it. They don't consider  
them to be a competition in the sense that they 
are doing something to kind of push this field  
ahead as well. And the more competition there 
is, the better you're able to build. And I feel  
like that's a very wholesome thing to kind of have 
as in in your founders thinking about as a whole  
kind of local and voice machinery is moving rather 
than, you know, how their product itself is just  
moving. I'm Div Garg, the founder and CEO of AGI 
Inc. We're building the world's truly personal AI  
that will be running on your phones and any 
other devices, including smart glasses and  
smart watches. We built our own on-device models 
that can go and take actions on your phone. So,  
you can control your whole phone and use any app 
for you. Right now, we're actually number one in  
the industry on benchmarks like Android world.
</details>

### 斯坦福 Transformer 课程与创立背景

>> 欢迎来到 CS 25 的第一堂导论课。我听说你在斯坦福创办了第一门 Transformer 课程，是这样吗？是的，我的本科是在康奈尔大学读的。在康奈尔时，我修了双学位，分别是物理和计算机科学。我以前在物理方面非常擅长。我曾经参加过国际物理奥林匹克竞赛，在印度拿过金牌。所以物理对我来说一直很轻松。后来我进入斯坦福攻读研究生。这实际上发生在我读斯坦福研究生的第一年。我注意到，斯坦福居然没有一门真正专门讲 Transformer 的课程。当时整个行业里的所有人都在关注 Transformer，因为那是一件极其重大的事情。斯坦福居然连一门相关的课程都没有，这感觉有些不可思议。对我而言就这么简单，我和另外两位朋友萌生了一个想法：如果我们直接去开设这门课会怎么样？于是，我们写了一份长达三页的提案，申请创办这门课程。在斯坦福由学生创设课程并不是常规操作。我们写好三页提案提交给斯坦福的院长，他们当时表示：“可以，我们非常有信心，这将会是一门精彩绝伦的课程。”我当时觉得这个构想太酷了，我应该直接去邀请我所能邀请到的最顶尖的大师。在那个时候，那个人就是 Geoffrey Hinton，他是 AI 领域的教父，并且获得了图灵奖。于是我直接去了他的个人网站，他的电子邮箱其实是公开的。所以实际上任何人都可以给他发邮件。我便给他发了一封邮件，说我正在斯坦福创办这样一个非常棒的全新系列课程，这是该领域的首创，询问他是否愿意来做一次演讲。结果他居然在 10 分钟之内就回复了，说他愿意来。
<details><summary>Original English</summary>
>> Welcome to the first and introductory lecture 
for CS 25. I heard that you make the first 
Transformer class in Stanford, right? Yeah,  
I was at Cornell for my undergrad. At Cornell, 
I was doing a double major. This was in physics  
and CS. I was just very good at physics. 
I actually did some international physics  
Olympiad where I won like gold medals in India. 
So, like physics has always been easy for me. 
And then I joined Stanford for my graduate 
studies. This was actually when I was my my  
first year at Stanford in the graduate program. 
I kind of noticed like okay, like Stanford didn't 
have an actual course on Transformers. It seems 
like the whole everyone in the industry cares  
about Transformers cuz that's a big thing. And 
it's kind of weird that like the Stanford does  
not even have a course on it. That's it for 
me and along with like two other friends,  
this is I just had the idea like what if 
we just go and create this course? Uh so,  
we actually wrote like a three-page proposal 
that we want to create this course. And so, and  
it's not normal for Stanford to create courses. 
And so, we actually wrote a three-page proposal,  
we sent it to the Stanford dean, and they're like, 
"Yeah, we were very confident and like this would  
be like a amazing." I just decided like this is 
a such a cool concept, I should just reach out to  
the best person I I can invite. At that time, that 
was Geoffrey Hinton, who was like the godfather of  
AI and has won won a Turing Award. So, I just went 
to his website, and his email is public, actually.  
So, so you can actually like anyone can email him. 
So, I just emailed him like I'm starting this like  
very cool course series at Stanford, uh which 
is the first of its kind, and you want to come  
and give a talk. And he actually replied within 
the within 10 minutes, saying like he's down.
</details>

>> 那大概是你在 AI 领域所能邀请到的最顶尖的人物了。在那之后，我们几乎把 AI 领域的每位知名人士都邀请来做过讲座。包括 Andrej Karpathy、Anthropic 的部分联合创始人，以及 OpenAI 的部分研究团队成员。因此，我们成功邀请到了业界最出类拔萃的人才来到斯坦福与学生们交流。后来我从斯坦福博士项目退学，并且拒绝了 OpenAI 的优厚 Offer，全力投身创办 AGI。为什么这个问题值得你押上一切？我认为这是我们当下能为全人类所做的最具影响力的事情。你如何度过每一天，以及你如何与技术进行交互，我认为这才是至关重要的。我喜欢描述这一点的一种方式，依然是借用《钢铁侠》中贾维斯的类比。想象一下，你拥有这样一位了解你一切的私人 AI 管家。你可以吩咐它为你办事。你和一个亿万富翁之间的区别在于，后者拥有一整支能够随时随地替他办事的团队。这使得那个人能够更具生产力，无论他是男是女。但现在，如果我们能拥有一支基本上可以替你打理一切的智能体大军，那层差距就被抹平了。因此你可以想象，全人类都将在同一个基准上被赋予平等的能力。而我们想要实现这一目标。你会如何形容 Steve？我认为他的优先级非常明确。他非常有条理，专注于核心关键事务，特别是在公司不断发展的过程中，清楚我们必须做些什么。他同样毕业于斯坦福，而且在做研究方面非常出色。我是 Steve，AGI 的联合创始人。为什么这项技术如此难以构建？我想一开始我更多关注的是操作本身。如果你要求它做这个，那就让智能体去执行那个动作。我们已经实现了这一步，而现在更多制约速度的瓶颈在于记忆与上下文。以及对你的深入理解——即便你给出的指令有些模糊，它仍然能够理解并执行你的真实意图，识别出你的潜在目的。最终甚至能主动预测出你需要什么，并提前为你办好。那么要达到那一步需要什么？信任与能力之间存在着相互依存的关系。如果你越信任这个 AI，越信任这个工具，你就会给它越多的上下文，让它越深入地理解你。如果它具备了这些，它就能变得更强大，并最终具备主动性。这关乎信任。归根结底，我们正在致力于让它完全在端侧运行。这意味着数据永远不会离开设备。没有云端需要你去托付信任。这就是最终目标。
<details><summary>Original English</summary>
>> And that's probably the best person you can 
invite in AI. We got like pretty much every famous  
person in AI to come and give a lecture at some 
point. Ambi Carbaty, some of the co-founders of  
Anthropic, some of the research team from OpenAI. 
So, we were able to get some of the best of the  
best people to come to Stanford and like talk talk 
to students. And I dropped out of my Stanford PhD  
and then turned down a million-dollar offer from 
OpenAI to build AGI. Why was this problem worth  
putting everything on? I think this is the most 
impactful thing we can do for the whole humanity  
right now. How you spend your day and how you 
interact with technology, I think that's what  
matters most. One way I like to just describe this 
is like again like going back to J.A.R.V.I.S. from  
Iron Man analogy. Like imagine like you had this 
you know like a personal AI butler that just knows  
everything about you. And you can ask it to like 
do things for you. The difference between you and  
a billionaire here has an army of people who 
can go and like do things for him. And that  
allows that person to be like more him or her. 
That allows that person to be more productive.  
But now if we can have an army of agents that 
can basically go and do everything for you,  
like that gap gets removed. So, you can imagine 
like the whole humanity gets equalized on the same  
basis. And we want to make that happen. How do 
you describe Steve? I think his priority is right.  
He's very like organized on like what matters, 
especially as the company is growing, what are the  
things we need to do. He's also like from Stanford 
and like very good doing some research. I'm Steve,  
co-founder at AGI. Why is this technology so hard 
to build? I think initially I was more focused on  
action. If you ask it to do this, then get the 
agent to do that. We've done that and now more  
of the rate limiters are memory and context. 
And having the understanding of you, even if  
you give it something that's kind of ambiguous, to 
still understand and be able to do what you meant,  
to recognize your underlying intention. And then 
ultimately to to proactively know that you would  
want that and then to do it for you. Then what 
do you need to get there? There's a relationship  
between trust and capability. If you trust the 
AI more, if you trust the tool more, then you'll  
give it more context. More understanding about 
you. You'll allow it to have more understanding  
about you. And if it has that, then it can be 
more capable and ultimately proactive. It goes  
into trust. Ultimately we're working towards 
running an all-on-device. And that means that  
the data never leaves the device. There's 
no cloud to trust. That's the ultimate goal.
</details>

### 技术架构与端侧落地的挑战

>> 我是 Naman。我是 AGI Inc. 的联合创始人之一。我主要负责大部分工程和研究工作。Div 是我哥哥，所以我从一出生就认识他了。针对非技术背景的人，你能否解释一下 AGI 的技术是如何运作的？我们的技术栈划分为三个主要部分。首先是你拥有的屏幕，以及屏幕上的多个 App。当用户发送一项任务时，我们会接收到该任务，同时也会截取屏幕画面。我们的智能体会查看这张截图，并理解截图内部需要执行什么动作，整个过程以循环机制运行。因此，我们拥有一个动作模型，它通过观察屏幕来预测下一步操作。这些动作被划分为点击、输入、滑动，接着这些动作会被映射回屏幕以执行具体任务。该循环会持续运行，直到达到最终状态。这包含了我们的测试框架以及推理引擎。总体而言，我们的架构由应用层、智能体底座以及推理层组成。那么瓶颈在哪里？最困难的部分是什么？让智能体完全在端侧运行。目前这部分功能完全部署在云端。而我们正在探索让它完全在设备本地运行。这样一来，所有的推理与计算都直接在设备内部完成。这项工作极具挑战性，因为一旦缩减模型尺寸，其能力往往也会随之下降。这就是我们的研究挑战所在：我们正在探究如何确保模型在尺寸缩小的同时，既能达到在大机器上运行的精度，又能具备足够快的速度。这才是真正为用户解锁隐私和安全的关键。如果某一天 OpenAI 或 Anthropic 也推出了能够通过语音直接控制手机的新功能呢？是的。那 AGI 怎么办，你们与他们相比有何不同？我们所做的很多东西实际上最终都会在设备本身运行。这与前沿大模型实验室的商业模式截然不同。我们愿景的核心在于：你不需要租用运行在别人云端的模型。它是完全在你的设备上运行的软件。因此，你拥有模型，你也拥有数据。而这正是前沿大模型实验室所不愿意看到的。例如，像 Anthropic 不可能直接向你交付一个可以在你设备端本地运行的模型，对吧？那么在那种情况下他们该如何盈利呢？当跨时区协作时，我们的团队会使用 WhisperFlow Note Taker。目前我们有两位设计师分别在首尔和旧金山两地合作推进周边商品设计。他们的作息时间重合极少，因此只能靠一次线上通话，任何细节都不能丢失。这正是 Note Taker 发挥作用的地方。在会议开始前，Note Taker 就已经根据日程邀请知道了参会者身份，并掌握了自定义词库中的专有术语。在 Google Meet 或任何其他平台上都不需要机器人入会。通话一开始，它就在后台静默运行。“嗨 Deion，你怎么样？”“嗨 Soyoung，我很好。这是我们新系列的暖腿套样品……”会议结束后，它会自动复查其记录的内容。会议摘要中会标注真实姓名，而不是“发言人一”和“发言人二”。次日清晨在首尔，未参会的同事直接向 Claude 询问会议决议，便能顺利接手推进。周边商品最终顺利交付给了位于旧金山的 AGI Inc 团队。WhisperFlow Note Taker 提供免费使用，你可以通过简介中的链接获取为期 1 个月的不限次会议 Whisper Pro 会员。
<details><summary>Original English</summary>
>> I'm Naman. I'm one of the co-founders at AGI 
Inc. I'm leading most of the engineering and  
research. There is my brother. So, I've known him 
since I was born. For non-technical people, could  
you explain how AGI technology work? Our stack is 
like divided into like three places. So, you have  
your screen and then you have like multiple apps. 
When a user sends a task, we get a task and we  
also get a screenshot. Our agent is able to take a 
look at this screenshot and then understand within  
the screenshot what action needs to be performed 
and it does it in a loop. So, we have a action  
model that looks at the screen and predicts next 
action. That action is divided into click, type,  
scroll and this action gets transferred back to 
the screen to perform task. And then this keeps  
running in the loop until we have reached our 
end state. This is where like our harnesses and  
we have our inferencing engine. So, our stack is 
divided into application layer, the agent harness,  
and then the inference. Where is the bottom 
neck? What is the hardest part? Getting the  
agent to be fully on device. This part is fully 
on the cloud side right now. And we are looking  
into making this running entirely on the device 
itself. So, all the inference, everything happens  
in the device itself. And it's a challenging 
because as soon as you decrease the model size,  
the capability is also decrease. And there it's 
our like research challenge where we are looking  
into how do we ensure that model is still like 
as accurate as like running on a bigger machines,  
and also it's fast enough. And this is what 
truly unlocks privacy and security for the users.  
What if OpenAI or Anthropic someday launches 
their new feature they can control their  
phone Yep. with their voice? What happens to 
AGI again and how's it different from that? So,  
a lot of stuff we are doing is like actually 
will be running on the device itself. And it's  
also very different from their business models 
Frontier Labs have. A big part of our vision is  
like you're not renting model running on someone 
else's cloud. So, it's like something that will  
be like running running fully on your device. 
So, like you own the model, you own the data.  
And this is something that Frontier Labs don't 
don't want. So, for example, they can topic is  
not like ship your model that will run on the on 
the device, right? So, how will they make money  
in that scenario? Our team uses WhisperFlow Note 
Taker when we work across time zones. Right now,  
two of our designers are making odds merge 
between Seoul and San Francisco. Their time barely  
overlaps, so they get one call and nothing can 
get lost. That's where Note Taker comes in. Before  
it starts, Note Taker already knows who's joining 
from the calendar invite and their own terms from  
the dictionary. No bot joins on Google Meet or any 
other platform. When the call starts, it just runs  
quietly in the background. Hey Deion, how are you? 
Hi Soyoung, I'm good. So, here's the calf warmer  
example for our new series on When the meeting is 
over, it double checks its own work. The summary's  
done with real names, not speaker one and two. 
The next morning in Seoul, a teammate who wasn't  
on the call asks Claude what was decided and 
picks it up from there. And the merch made it  
all the way to the AGI Inc team to San Francisco. 
WhisperFlow note taker is free to use and you can  
get 1 month of Whisper Pro with unlimited 
meetings with the link in the description.
</details>

### 产品演示：语音跨应用点外卖

>> 我叫 Will，我的职责范围涵盖增长以及可穿戴设备和硬件部门。你能分享一下我们能用 AGI 做些什么吗？当然可以。大家都见过打 Uber 和回复邮件这种传统演示，但除此以外还有很多事情可以做。我们在消费者场景和无障碍交互方面投入了大量精力。设想一下，如果老奶奶只需要说：“嘿，你能帮我在 DoorDash 上订一份新鲜的纯豆腐汤吗？”或者说：“嘿，我不会用这台手机，你能帮我打开 FaceTime 打给我孙子吗？”那我能现场点一份我们现在的午餐吗？完全没问题。我来向你演示它是如何运作的。这里可以看到来自不同渠道的一系列预设指令，但今天我们直接输入一条自定义提示词。我们现在大概有四个人，你想来一份定制的 Chipotle 套餐吗？我让你来挑选食材。“嘿，我想要一份 Chipotle：牛排肉、糙米饭、生菜、玉米、鳄梨酱、萨尔萨辣酱、酸奶油加一些奶酪。在 DoorDash 上下单。”
<details><summary>Original English</summary>
>> My name is Will and I cover the scope 
of growth as well as the wearables  
and hardware departments. Can you share 
what can we do with AGI? Absolutely. So,  
everyone's seen the traditional demos of 
ordering Ubers and responding to emails,  
but there's a lot of other things you can do. We 
spend a lot of focus on the consumer side as well  
as the accessibility side. Imagine if like the the 
grandmother could just say, "Hey, can you help me  
order DoorDash for some fresh soondubu?" Or "Hey, 
I don't know how to use my phone. Can you pull up  
a FaceTime and call my grandson?" So, then can I 
like order a lunch for us right now? Absolutely.  
I'll show you how it works. Right here you see a 
bunch of presets from all the different channels,  
but we'll just do a custom prompt today. So, I 
guess there's like four of us, so do you like  
a custom like Chipotle set? I'll let you pick like 
the the ingredients. Hey, I want a Chipotle steak,  
brown rice, lettuce, corn, guac, salsa, sour 
cream, and some cheese. And order it on DoorDash.
</details>

>> 看，它在不需要手动干预的情况下自动打开了应用。
<details><summary>Original English</summary>
>> So, it just pulled up the app hands-free.
</details>

>> 正如你所看到的，它正在逐项点击每个条目。现在它正在点击牛排。选好了糙米饭、黑豆。
<details><summary>Original English</summary>
>> As you can see, it's hitting each individual 
parcel. Right now, it's clicking the 
steak. Got the brown rice, black beans.
</details>

>> 它刚刚完成下单准备。马上就要下单了。然后屏幕上弹出一个确认提示：“您确认要以 91 美元提交这笔订单吗？”我们始终将其作为一层安全护栏。
<details><summary>Original English</summary>
>> So, it just placed the order. It's about to place 
order. And then right here it says a prompt,  
"Would you want to place this order for 
$91?" We always have it as like a guard rail.
</details>

>> 太棒了。大家可以看到订单已经成功下达。任务完成。太酷了。简直绝了。
<details><summary>Original English</summary>
>> Nice. So you guys can see that where this placed. 
And uh Task complete. That's dope. Hell yeah.
</details>

### 从技术 Demo 到商业落地的闭环

>> 你如何将那个演示转化为一门真正的商业生意？是的。你必须找到客户，并且让用户真正热爱你的产品。这就像：你可以造出很酷的新技术，但别人凭什么要买它？别人为什么要用它？你能创造什么价值？所以我们花了很多时间去深入了解人们在日常生活中可能遭遇的摩擦与痛点。当时我们脑海里有很多想法，正在尝试不同的路径。有一次我们甚至去了金门公园，当时那里正在举行音乐节。我们跑到音乐节门口，给人们派发 Powerade 饮料等物资，借此与潜在客户建立互动，看看能否收集到一些真实反馈。当时我们已经提前约好了相关会议，所以那不是我可以拖上一个月的事情。我必须在无数次迭代中弄清楚自己到底能交付出什么。最终，我成功开发出了切实可行的方案。在那两周里我开启了极限冲刺模式，每天基本上就睡在办公室 3 到 4 个小时，只为了把事情彻底搞定。奇迹般地，我成功开发出了有史以来首个从未有人成功打造过的 Android 端智能体。你们与高通等大公司建立了合作关系。你们是如何赢得这些大公司青睐的？从某种意义上说，这感觉非常纯粹。那完全是通过技术演示实现的。他们会惊叹道：“哇，我以前从没见过手机能做出这种操作。”而那是我们的手机、我们的芯片在运行它。太酷了。我们还能做些什么？我们敏锐地察觉到了这些大公司存在这种需求，当时没有任何人在填补这一空白，而我们能够做到。我认为关键在于选好你的战场。如果你能把电子表格自动化，那会是一门极好的生意；如果你能把人们在电子表格里做的一切事情完全自动化，你肯定能取得成功，但同时有 10 家其他公司也在角逐那个赛道。那是一个经过验证的庞大市场。而我们走的是一条更为少见的道路——为边缘端设备构建智能体。确实有一些公司对此有明确需求，尤其是那些制造设备本身的硬件厂商。当时几乎没有人在真正主攻这个方向。我认为我们至今仍然是最好的。与我们合作的公司依然评价我们在该类别中居于领先地位。
<details><summary>Original English</summary>
>> How do you make that demo into a real business? 
Yeah. You need to find uh customers and you want  
to have people like users who love your product. 
Like it's like okay, like you can build this new  
cool technology, but like why would someone buy 
it? Why would someone want to use this? And what  
value can you create? And I just so we've been 
spending a lot of time like understanding like  
the friction pain points people might 
have in their daily lives. So that time  
we still had a lot of ideas where the trying 
different ideas. One time even we went to the  
Golden Gate Park and there was this a music 
festival going on. We went in front of the the  
festival. I was like giving away the like 
Powerade and stuff to kind of get engaged with  
the potential customer and then see if they get 
any feedback. And then we had the meeting already  
set up. So it's not something that I can take a 
month. So I had to really understand what I can  
deliver out of the million iteration. Finally 
that I was able to invent the one that works.  
I was a little bit crunching like 2 weeks to 
literally sleeping in the office like 3-4 hours to  
really get things done. Miraculously that we 
I was able to invent the the first time ever  
the Android agent that no one had been ever 
built. You guys are partner with big companies  
like Qualcomm and other big companies. So how 
did you get those companies? Like it felt it  
felt very pure in a way. It was like it was tech 
demos. They'd say, "Wow, I've never seen I've  
never seen a phone do that before." And that's our 
phone, that's our chip that's running that. Cool.  
Uh what more can we do? I guess that we saw that 
there was a need for this by these big companies  
and no one was filling it and we could. I think 
it's like pick your battles. If you can automate  
spreadsheets, that's a great business. You will do 
well if you can fully automate everything people  
do in spreadsheets, but there's 10 other companies 
going after that. Large proven market. There's  
this more unusual path where we can build it for 
edge devices and there were definitely companies  
that wanted it, especially the ones that make 
the devices. No one was really going after that.  
I think we're still the best. Companies we work 
with still say we're the best in in that category.
</details>

### 复合错误率与真实生产环境的挑战

>> 我想说，构建一个所谓的演示原型与构建生产级技术之间存在巨大的鸿沟。因为一个演示可能只有 10% 的成功率，在早期这完全没问题，因为你只是在验证可行性的上限。但如果你未来要在某个时刻向十亿以上的用户交付产品，你就必须进行极其严格和鲁棒的测试。自动驾驶汽车就是一个很好的类比。想想 Waymo 和特斯拉，它们实际上在十多年前就开始研发自动驾驶了。而从概念验证走到能够在道路上实际行驶的真实车辆，花费了他们整整 10 年的时间。因为真实世界中存在海量的边缘案例，随时可能导致系统故障或运行出错。我认为面对那些复杂场景，当前成功率可能只有 20% 左右。在茶水间里，我看到你正在向创始团队解释和展示一些东西。你能简要说说那是什么吗？噢，那是我们智能体的基准测试表现。基本上，我们试图对我们在不同 App 中的执行效果进行分类评估。在某些 App 上表现良好，但在某些 App 上却并不理想，因为用户的行为非常多样且独特。我的意思是，有些人会要求 AI 智能体执行一些极其离奇的任务。比如呢？有人要求让智能体帮他报税……手机也能报税？是的，这就是我所说的。存在各种非常奇特的用例。单个智能体在演示中可以表现得十全十美。但一旦你将它放入现实世界——只要你把智能体从一切受控完美的沙箱环境中拿出来，现实世界充满了混乱。对我们而言，这才是真正展现挑战与核心价值所在的地方：智能体在生产环境中是否真的能表现优异？假设智能体在单步轮次中的准确率是 96%，这看起来不错。但如果你的任务跨越了 10 到 20 个步骤，这些错误实际上是会逐级累积复合的。如果一个智能体单步准确率是 90%，在连续执行 20 步任务后，整体准确率实际上会骤降到 40% 左右。而这正是我们要攻克的难题。人们之所以来找我们，正是因为我们是唯一真正切实致力于解决这一痛点的团队。有了记忆模块，你就可以去设计……是的，因为我觉得那样会为我们提供更多上下文。好的，那我是否可以对当前存储的内容进行全盘重新设计？完全可以。你可以先拟定一份方案，如果你想做实验，做完后可以展示给我看，比如说明：“这是具体的改进点，你可以看到这里变得更好了。”好的，我正在着手制定方案，目前还没有在看板上修改任何实际内容。我大概在两到三小时内向你展示，届时我也可能会邀请你进入看板、Cloudflare 以及研讨会环境。这样一旦你完成了修改，你就可以在当前代码测试环境看到改动生效。好的，没问题。
<details><summary>Original English</summary>
>> I'll say there's a big difference between 
building a called like a demo prototype versus  
a production level technology. Because like it's 
possible like the demo only works 10%of the time,  
it's fine. Because like you're like testing 
out what's possible. But then if you're like  
shipping something to a billion plus users at 
some point, then you just need to like robustly  
test it. So a good analogy is like self-driving 
cars. Like if you think at like Waymo and Tesla,  
they have they actually started like working 
on self-driving cars like more than a decade  
ago. And it took them like 10 years to go from 
like something that was a concept to an actual  
thing that you can drive on the roads. Because 
like there's so many like edge cases in the real  
world where like things can fail, like something 
might go wrong. I think with the complex ones,  
it's like 20 20% In the kitchen, I saw you were 
explaining and showing something to founders.  
Could you briefly explain what was it? Oh, that 
was our baselines of our agent. So basically, we  
were we were trying to categorize how we perform 
across different apps. Some apps, if it was good,  
some apps, it's not the best because like users 
are very unique. And what I mean by that is like  
some people ask some really interesting things 
to do with an AI agent. For example? One person  
asked like file their taxes like so you know 
Uh can't do that. phone? Yeah, so that's what  
I mean. There's like pretty interesting use 
cases. A single agent can be like perfect in a  
demo. As soon as you take it to the real world 
like as soon as you take agent from a sandbox  
environment where everything is fully perfect, the 
real world has there's so much chaos. And for us,  
like, that's where, like, the real challenge and 
real value at shows is. Can the agent actually do  
work really well on production? If the agent 
is, let's say, 96%accurate on a single turn,  
that is fine. But, let's say you're 
running across 10 or 20 different tasks,  
those errors actually compound. So, if an agent 
was 90% accurate, after 20 tasks, it actually  
decreases around 40%accuracy. And that's what 
we are trying to solve. And that's what, like,  
people are coming to us for because we are the 
only ones who are actually really solving that  
challenge. So, with memory, you can design Yeah, 
because I I Yeah, I feel like that would give us  
more context. Okay, so, I am like allowed to kind 
of do a whole kind of redesign of what is being  
stored There is So, maybe create a plan, and if 
you want to experiment it, and then like show me,  
and be like, "These are the improvements. 
You saw this which is becoming better." Yeah,  
I'm I'm working on making a plan. I'm not 
editing anything in the board right now. So,  
I'll show it to you by the by like in like 2 3 
hours, and then I can I'll probably also invite  
you to the board cloud fair and workshop. So, that 
way you have access to Once you make the changes,  
Okay. you can actually see in the environment 
key test on this code here. Okay. Yeah.
</details>

### 人才试用机制与夜间工程文化

>> 你刚才向他问了什么？我刚才在问他关于存储在数据库里的数据的问题……在一般的公司里，新人入职第一天就直接上手处理生产级代码是非常少见的。当你招聘新员工时，你们是如何决定他们具体负责哪块业务的？这取决于具体的角色定位以及他们是以何种身份加入我们的。通常我们的做法是先进行试用期考核，然后再转为全职录用。以他为例，他目前正处于第一周的试用期。我们交给他一个我们希望落地的年度功能模块，并设定了预期产出目标。我们借此观察这个人在面对较为模糊的需求时表现如何，是否能主动提出极其优秀的解决方案。我们同样想检验他们在提出产品构想方面的能力。我们希望开展更多的头脑风暴与迭代循环。比如抛出一个可以考虑的功能，或者探讨什么功能对用户而言才真正有价值，然后不断迭代优化它。我们将其视为持续的迭代：不断打磨优化，直到它能够持续吸引用户并让用户产生真正的粘性。对于全职员工，我们要求他们具备独立思考的能力。通常我希望自己扮演的角色是负责验证想法是否正确，或者充当最终评估决策的一道防线。
<details><summary>Original English</summary>
>> What did you ask to him? Uh so, I was asking 
him about the data that is being stored on the  
database is not seen very quickly at companies 
to be working on production grade code at the  
very start at the very first day. When you hire 
a new employee, how do you decide what are they  
going to be in charge of? So, it does depend 
on the role, like, what's the role and like in  
what capacity are they joining us. So, typically 
what we do is, like, we actually do, like, trials,  
and then do a full-time hire. So, in this case, 
he is on a first-week trial. So, we give him,  
like, a year's of feature implementation that he 
want, and here are the outcomes. We are seeing,  
like, how good a is the person in terms 
of, like, taking this, like, a bit more  
ambiguous request in and actually coming up 
with, like, a really good suggestion. So,  
what we try to do is also see how good are they 
at like coming up with product ideas. And we want  
to do like more like brainstorming and iteration 
cycle. So, here's a feature you can think of or  
just what I see is like really useful for the user 
and then we want to iterate and like keep refining  
it. We see this as like a constant iteration. 
You just keep refining, optimizing it until it  
keeps attracting the users and make them actually 
truly sticky users. And for full-time employees,  
we actually like them to be like independent 
thinkers. Typically, I want to basically be  
the person who's validating the ideas correct 
or just like be the final layer of judging.
</details>

>> 嗨。嗨。你们开完会了吗？你们平时一般在这个时间点开会吗？是的。这场会议是晚上 10:00 开始的，是和我们印度的远程团队开会。所以对他们来说现在是早上。但这种节奏挺好的，因为我们有了自主的时间。我们在晚上拥有完全属于自己的空间，没有任何人会来打扰我们，我们可以完全专注于产品。是的，我认为这个功能……我认为这个东西会引发大量的……你叫它什么来着？说得很有道理。是的，我认为我们可以这么做……对，现在是讨论这个的好时机。我们聊聊吧。AGI 觉得世界上有很多人与我们同行。这种深夜俱乐部般的文化是从哪里来的？是的。我一般睡得很晚，有时要到凌晨两点甚至更晚。我只是觉得在深夜更容易集中注意力，因为没有任何干扰。没有人在通讯软件上发消息找你，也没有人发邮件。完全没有干扰。没有任何人催你。只剩下你和你正试图解决的问题。正因如此，我们形成了这样的公司文化——大家喜欢工作到很晚，因为在这个时段，大家觉得能够持续贡献产出，把事情搞定。我个人的疑问是，这样 24/7 全天候高强度工作真的具有可持续性吗？我认为，如果你热爱你所做的事，这就无所谓了。如果你真的是在全力以赴构建某种你坚信具有极高价值、人们一定会想去使用的产品，那么你为此付出的牺牲就是富有意义的。我想说我们非常强调自治。只要你的产出达到一定的水准，你在自己负责的事情上就拥有很高的独立性。你掌控自己的决策，由你去落实落地。大家非常喜欢这种模式，因为他们能够尽情释放自己的创造力和才华。我认为这是非常有成就感的。看到自己亲手创造出来的东西在未来被数百万人使用，我认为这是你一生中所能经历的最具成就感的事情之一。
<details><summary>Original English</summary>
>> Hi. Hi. Did you finish your meeting? Do you 
guys usually have meeting at this time? Yes. So,  
that one started at 10:00 and that's 
with our remote team in India. So,  
it's morning for them. But, it's good cuz we 
have space. We have space in the evening. No  
one else will bother us. We can just focus on 
product. Yeah, I think this feature I think  
this thing is going to get a lot of what do you 
call it? That's a good point. Yeah. I think we  
can do Yeah, it's a good time for that. Let's 
talk. AJ thinks like there are many people who  
are in our world. Where Where is this night 
Yeah. culture club? I sleep pretty late like  
sometimes like 2:00 a.m.s or later. I just 
find it easy to focus at night because you  
don't have any distractions. No one is pinging 
you or sending an email. There's no distraction.  
There's nobody pinging you. It's just you and 
like the things that you're trying to solve.  
And that's where we see the our culture where 
like people like to stay longer because that's  
where they see they want to keep contributing. 
They want to get it. My personal question is,  
is that like really sustainable working 24/7? 
I think like if you love what you're doing,  
it doesn't matter. It's like if you really are 
looking into building something that you truly  
see is like a really value add, people would 
want to use it. It's like a meaningful sacrifice  
that you are going to do. I'll say we try to be 
very autonomous. There's a certain independence  
on things you're working on as long as you're 
like performing at a certain bar. So, you are  
like in charge of your decisions, so you make 
them happen. People really like it because like  
they can like unleash all their creativity and 
the talent. And I think that's very fulfilling.  
Um to like see that like something I've created by 
yourself is now getting used by millions of people  
over time. And I think that's like one of the most 
fulfilling things that you can do in your life.
</details>

### 线下社群、硬件实验与文化塑造

>> 线下活动成本很高。你需要支付餐饮、物料以及所有费用。那么 AGI 为什么还要坚持频繁举办活动？活动对我们来说至关重要。我们在做端侧研发，因此需要大量极其聪明的优秀研究员加入我们的团队，我们非常喜欢把大家聚在一起探讨这一主题。线上的数字化沟通现在价值被大幅稀释了。你根本分不清联系你的是不是某个人的智能体，也无法确定信息的真实度。我经常注意到，如果人们意识到对面是一个 AI 实验室发来的泛化消息，往往直接就不读了。因此，与人面对面相识是建立真实连接的最佳途径之一。而且有时候，你根本预料不到仅仅通过一次面对面的深入沟通会碰撞出什么火花，对吧？他们可能会帮忙引荐，可能会为你介绍客户，也可能会推荐人才加入团队。所以从长远来看，线下活动会产生巨大的复利效应，并带来很多意想不到的机缘。在这家公司里你最喜欢的是什么？我在这家公司最喜欢的是给予我们的创作自由背后的信任。在早期，你一旦明确了自己擅长什么，他们就会给予你充分的自由去把项目完整做出来。例如，我们会组织一次公司团建，然后去发布 100 台类似迷你手机的设备。是的，这就是迷你手机的原型，对吧？稍微有点厚实，有点像以前的 iPod。其背后的设计初衷是：当你看到这样的东西时，它会激发你的好奇心，你会不禁发问：“咦，这能用来发短信吗？你平时怎么操作它？”它就像一个现代版的寻呼机。你只要对着它说话，它就会替你完成所有操作。这仅仅是我们在公司内部正在酝酿的众多有趣实验中的一个而已。所以你很热爱 AGI。我热爱 AGI。这实际上是我对公司的第一项贡献。噢，这我以前还真不知道。这是我的第一项贡献。自从参与了这个项目之后，我就成了这个大家庭的一份子。要说最核心的部分，我不确定……看看眼前这位。CK？这是公司的顶梁柱老大哥。没有 CK，我们绝对走不到今天。CK 是团队文化中极其重要的一部分。团队文化？文化本身也是高度动态变化的。我觉得文化是无法强行灌输的。文化是由加入团队的每一个人共同塑造出来的。大多数公司都倾向于“快速招聘，快速解雇”。我们则走了一条不同的路径。我们招聘极其谨慎缓慢，但淘汰决断非常果断，因为要找到一个文化契合的人非常困难。某个人可能过往业绩斐然，可能是业内业务能力最强的人，但在他们真正进入团队与你共事之前，你根本无法确认文化上是否合适。因此，对于引入这个环境中的每一个人，我们都非常谨慎，因为最后加入公司的每一个个体，都会为这里的文化增添新的注脚。
<details><summary>Original English</summary>
>> In person events are expensive. You have 
to pay for food, stuff, and everything. So,  
why does AGI keep hosting events? Events are 
like big for us. We're building for on-device,  
so we need a lot of very smart researchers to 
join our team, and we just like love bringing them  
together and discuss the topic. Digital becomes 
discounted a lot. You know, it's like you didn't  
know if it's someone's agent reaching out to you, 
and you don't know if the information is accurate.  
And like I noticed a lot like a lot of times if 
people are recognizing the AS labs, you just like  
stop reading. So, meeting someone in person in 
person is one of the best ways to actually build  
connection. And sometimes you don't know what's 
going to happen if you just have one discussion  
with a person, right? They can make an intro, 
they can introduce you to a client, they can refer  
someone to work for you. So, overall events, they 
just like compound a lot, and they drive a lot of  
serendipity. What's your favorite thing in this 
company? My favorite thing in this company is the  
the trust behind the creative freedom we're given. 
Early on, you identify like what you're good at,  
and then they just give you the freedom to really 
build out like the project. For example, we'll do  
a a company trip, and we'll go release like a a 
hundred mini phones. Yeah, so like this is like an  
example of like a mini phone, right? A little bit 
chunky, a little bit like an iPod. Uh the thought  
process behind this is like when you see something 
like this, it sparks a sense of curiosity, and you  
ask a question like, "Huh, like are you texting 
on it?" And like how are you interfacing with  
this? It's like a modern-day pager. You You speak 
into it, and it makes all the actions for you. So,  
this is just like one of the many different 
interesting experiments we're cooking in the  
company. So, you love AGI. I love AGI. This is 
my actual first contribution to the company. Oh,  
I didn't know that. This is my first contribution. 
Uh ever since this project I've been uh I've been  
uh part of the family. The biggest part, like I 
don't know. Look at this Look at this man right  
here. CK? This is the big brother of the company. 
Without CK, we really wouldn't be anywhere. CK is  
a big part of the team culture. Team culture? 
Culture is also very dynamic. I feel like a  
culture cannot be enforced. A culture is formed 
by every single person that joins the team.  
Most companies have this tendency of hiring fast 
and firing fast. We take a different route. We  
hire really slow, but we fire very fast because 
it's difficult to find culture fit in a person.  
Someone can be a great former. They can be the 
most skilled person in the industry of their job,  
but you don't really know the culture fit until 
they actually come and work with you. And so,  
we're very cautious about the people that we 
bring into this environment because every last  
person that joins this company adds on to the 
culture.
</details>

### 新操作系统：重构人与屏幕的关系

>> 在未来，我们坚信世界上可能会存在数十亿个个性化模型。每个人都会拥有专属于自己的模型。那个模型能够实现自主持续学习，它学习关于你的一切，学习你的偏好，并变得越来越懂你。你可以给予它百分之百的信任，因为你真正物理上拥有这个模型，它是属于你的资产。这就像你拥有一辆车，你可以改装这辆车，在里面加装部件等等。现在的状况绝非像全世界每个人都开着一模一样的通用汽车，对吧？而目前的大模型市场正是这种统一泛化的状态。因此，我们希望提供这样一种路径：你可以购买模型、定制模型，让它不断学习关于你的偏好。随着时间的推移，每个人都会拥有专属的高度个性化模型。所以，选择哪款 AI、是由哪款 AI 在替你执行这些操作，以及那个为你服务的 AI 在系统设计时融入了什么考量，都是至关重要的。这可能会演变成一种比所有人际关系都更具影响力、或者至少与人类之间的关系同等重要的纽带。我们看到这一切正在不断演进。我发自内心地希望置身于这样一个世界中：我能够真正为让世界变得更美好贡献自己的力量。我想看看我们能把它推向多么遥远的边界，看看自己是否能真正为改善每个人的现实生活做出贡献。我觉得，面对普通大众，你不需要跑去对别人说：“看，我为你做了一个极其出色的智能体。”对普通人而言，它的一大核心意义在于：你可以减少盯着屏幕的时间，把更少的时间耗费在屏幕前，把更多的时间留给真实的生活。你可以直接对着手机、手表或任何设备上的 AI 说话，当手机放在口袋里或留在家里时，它就能在后台默默替你办好所有事情。现在，我们思考自己正在构建的产品时，绝不仅限于“噢，我们只是在做一个用来控制 App 的智能体”，而是一整套完整的体系。它是为各类设备打造的全新操作系统，旨在帮助你减少对屏幕的依赖，更多地回归真实生活。其实，我们为各位准备了一份小伴手礼。这是送给我们客人的小礼物。谢谢你们。太棒了。对，看镜头，笑一笑。非常感谢大家。
<details><summary>Original English</summary>
>> In the future, we believe there could 
be like billions of personalized models. And like  
every person gets their own model. That model can 
be just like self-learning. It's learning things  
about you, your preferences. It's getting better 
and better. And you can fully trust it because you  
actually have the model like it's like like it's 
yours. It's like how you have a car and you can 
modify your car and put things in and whatever.  
It's not like you have one generic car that serves 
every single person on Earth, right? And that's  
what's happening with models right now. So, we 
want to have this way where you can buy the model,  
you can customize it, learn things about you. And 
then over time, like everyone gets their own very,  
very personalized model over time. And so, 
choosing that AI, which AI is doing that,  
what went into the design of the AI that does 
that for you, is very important. That might be  
a more influential relationship than any human 
relationship or at least as influential of a  
relationship as any human relationship. And 
what we see is it's going to keep changing. I  
really want to be there in the world where like I 
actually contributed in making the world better.  
I want to see how far can we take it and like 
can I actually really contribute in the world  
actually making everyone's lives better. I think 
it's like you don't you don't go to an everyday  
person and say "agent, I made a great agent for 
you." One thing it can mean for people is that  
you look at your screen less and you spend less 
time on the screen and more time in real life.  
You can just talk to your AI from your phones or 
your watch or whatever and then it can be doing  
things for you in the background while your phone 
is in your pocket or at home. Now, the way that  
we think about what we're building is not just 
oh, we're making this agent to control apps,  
but it is this whole system. It's this new 
operating system for devices that help you  
look at the screen less and be more in real life. 
Actually, we brought the small gifts for you guys.  
These are the small gifts for our guests. Thank 
you. Oh, that's good. Yeah. Cheese. Cheese.
So, thank you guys.
</details>