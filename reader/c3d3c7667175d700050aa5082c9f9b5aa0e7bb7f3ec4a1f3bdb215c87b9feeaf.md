---
author: AI Engineer
date: '2026-08-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=S6aSoQ6_u5A
speaker: AI Engineer
tags:
  - embodied-ai
  - robotics
  - ai-agent
  - vla-model
  - edge-computing
title: 用自然语言指挥机器人：基于 Strands 智能体框架的具身智能实践
summary: AWS 工程师 Sandhya Subramani 展示了名为 Scout 的智能漫游车，通过开源框架 Strands Agents 与多 Agent 架构，使传统机器人具备自然语言理解、环境感知及自主决策能力，并阐述了云边协同与具身智能的发展趋势。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - AWS
  - Anthropic
  - OpenAI
products_models:
  - Strands Agents
  - Claude Opus
  - OpenAI Realtime API
  - Raspberry Pi
media_books: []
status: evergreen
---
### 介绍漫游车 Scout 与具身大脑

**Sandy**: 大家好，我叫 **Sandy**。今天来见见我的搭档 **Scout**，这是我的友好漫游机器人。通常大家可能会认为漫游车不会自己思考，对吧？我们必须告诉它们做什么，或者必须非常具体地通过编程设定它们如何思考。但眼前这个小家伙其实拥有一个“大脑”，它能够自主思考。

让我把屏幕切换给你们看。糟糕，切到错误的屏幕上了。我看看怎么停掉这个，然后切换到我的屏幕。请稍等我一秒钟，我先结束放映，然后切过来。

这就是 Scout 正在观察的画面。Scout 在这里有一个小小的“大脑”，能够用**自然语言**理解我对它说的话。例如，如果你们能看到我的屏幕，我在上面输入：“嘿 Scout，打开你的车灯，向大家打个招呼。”

它实际上能够理解并执行这些动作。

<details>
<summary>Original English</summary>

**Sandy**: Hello everyone. My name is Sandy and meet my co-host today, Scout. This is my friendly rover. And one would think that rovers can't really think for themselves, right? We have to tell them what to do or we have to very specifically program them on how to think. But this little guy here actually has a brain and he can think for himself.

Let me show you my screen. Oh no, it's going to the wrong screen. I'm going to see how I can stop this and I'm going to see how I can move to my screen. Um, give me just a second. I'm going to end show and then we get to this.

So this is what Scout here is looking at. And Scout here has a small little brain. And Scout can understand what I'm saying in natural language. For example, if you can see my screen here, if I say, "Hey Scout," I'm going to type to him. Say, "Hey Scout, turn on your headlights and say hi to everyone."

He is actually going to be able to understand and do those actions.

</details>

### 硬件架构与实时交互演示

**Sandy**: 但它是怎么做到这些事情的呢？它需要思考几秒钟，因为这里的架构配置是：它的车身安装了一块 **Raspberry Pi**（树莓派），这块树莓派实际上放置在纽约市的一个小地方，而车上插了一张 SIM 卡，通过 **4G 连接**与树莓派通信并接收信号。

所以它会反馈说：“收到，正在执行。”

你们看，我要对它说：“转个圈。”哦不，它其实正在对我说话。它说：“我看到了舞台，看起来棒极了。左边是大屏幕，有明亮的舞台灯光，还有一排排观众席。”

我接着问：“你能看到几个人？”我从来没有针对这个问题训练过它，让我们看看它能不能答对。它思考了一两秒：“让我从前置摄像头好好看一下。我看到了两个人，一个在舞台后方的演讲者监视器附近，另一个人在更靠右的位置。”

然后我让它：“原地转圈 360 度。”它还问：“这场演讲快要开始了吗？”所以它马上就会原地旋转 360 度，然后可能会惊叹自己做到了。

<details>
<summary>Original English</summary>

**Sandy**: But how is he able to do these things, right? It's going to take him a couple of seconds to think about it because how this has been set up is he is working on with a Raspberry Pi installed and that Raspberry Pi is actually in a small little location in New York City and he's got a SIM card here which is then connecting to that to that Raspberry Pi and then he's getting signals. So, this is via 4G connection. And so, he's like, "Oh, hey, on it."

And if you can see, you know what? I'm going to tell him, "Spin around." And oh, no, he's actually speaking to me. He's like, "I see the stage and it's looking great. Big presentation screen to the left, bright stage lights, and rows of seats for the audience."

How many people do you see? I've never trained him to answer this question, but let's see if he's getting it. He's thinking for like a second or two.

"Let me take a good look from the front camera. I see two people. One near the speaker monitor set up at the back of the stage and another person further right."

Nah. Spin 360 and he's also saying is this session about to start right so he's going to spin 360 any second now and then he's probably going to be like oh wow I did.

</details>

### Strands Agents 智能体分层与核心能力

**Sandy**: 这个小机器人代表了新一代的机器人。看，它现在正在做 360 度旋转，并且在汇报它所看到的内容，它说：“让我们转起来吧！”

这一代新型机器人与传统的机器人训练完全不同，因为我赋予了它一个小小的“大脑”。所谓赋予它大脑是什么意思？我为它增加了一个**智能体层（Agentic Layer）**，采用的是由 **AWS** 开发的开源框架 **Strands Agents**。

我快速切回幻灯片，大家可以看到：机器人本身具备一些已有的底层工具，它能够自主执行某些固定的动作，但也仅限于这些预设动作。我们所做的就是在其上加入一层 **LLM**（大语言模型），更准确地说，是加入一层 **Agent**（智能体），由智能体负责编排并决定调用哪一个工具，从而让机器人真正开始执行我们期望的任务。

在传统的软件工程与 AI 工程中，我们为智能体提供软件工具；同样地，我们也可以为同一个 AI 智能体赋予一个名为“机器人”的**硬件工具**。这个硬件工具拥有预设函数或可编程策略（Programmable Policies），智能体可以自主决定在何时执行哪种策略。

因此，只需一个机器人智能体，我们就能让它完成无数种新任务，并让它理解我们用自然语言所传达的指令。

那么该如何上手呢？通过 Strands 智能体 Harness，仅仅需要**五行代码**。我们所要做的就是导入 `strands_agent`，调用机器人工具，定义 `tools = [robot]`，然后输入指令：“捡起红色的方块。”假设机器人硬件具备相应能力，它就能够完成捡起红色方块的操作。

<details>
<summary>Original English</summary>

**Sandy**: So this little robot here is a next generation of robot where ah there we go he is spinning 360 now and he's probably going to tell me what he's seeing and he's saying let's spin. Right?

So this new generation of robots is it's different from our traditional robot training because I have given this guy a little brain. And what do I mean by I've given him a brain? I've given this robot an agentic layer and it's called strands agents which is an open-source framework which was built by AWS and I'm going to quickly go back to my slide deck we can see it right and so here what happens is we have these existing tools that the robot can do he can take certain actions by himself but only those actions by himself so what we can do is we can add a layer of LLM or even better add a layer of agent to it so that the agent orchestrates which tool to call and how to really get the robot to start doing the things we want.

So in traditional software with traditional AI machine like AI engineering we can give agents software tools. Similarly, we can give the same AI agent a hardware tool called a robot which has access to preset functions or programmable policies and then the agent can decide which policy to implement when. So all it takes is one robot agent for us to be able to do new innumerous tasks and have it understand what we're teaching it in natural language.

So how do we get started with it? All it takes is five lines of code. This is through the agent harness called strands. And all we have to do is import the strands agent and call the robot tool. And we say tools equals the robot and then we say pick up the red cube and should be able to pick up a red cube assuming that the robot has that capability. Yeah.

</details>

### 三 Agent 协同系统：思考、通信与语音

**Sandy**: 瞧，它看到了某个人，就兴奋地说：“让我朝那个人走过去。”

这个小家伙非常特别，因为它身上运行的不是单一的智能体，而是**三个不同的 Agent**。这三个 Agent 全部基于 Strands 构建，并且同时并行协作：

1. **思考智能体（Thinker Agent）**：这是它大脑中负责持续思考、评估周围环境并决策“下一步该做什么”的部分，处于时刻运转的状态。
2. **通信智能体（Communication Agent）**：稍后我会向大家展示，我将它接入了我的 **Telegram** 应用和 Web 端应用，使它能够与我进行自然语言对话，并根据我的指令去采取行动；除此以外，它也能自主感知、思考并决定要做什么。
3. **语音智能体（Voice Agent）**：它拥有的第三类智能体是语音交互 Agent。不过我刚才不得不暂时把它禁用了，因为现场只要我一开口说话，它就会以为我在跟它聊天，然后不断插话，我们的联席主持人就会一直打断我。所以我暂时关闭了语音功能。

但本质上，这三个智能体与这台机器人协同工作，从而赋予了它远超基础训练与既定策略的大规模自主行动能力。

<details>
<summary>Original English</summary>

**Sandy**: Now he's seen someone and he's like oh let me go towards that person. So he gets pretty excited.

This guy is pretty special because he doesn't have just one agent. He's got three different agents. All three of them are strands and all three of them are working simultaneously.

One of them is the thinker agent and that's the part of him that's constantly thinking and assessing the environment and like what do I do next? And that part of his brain is constantly thinking.

Then there's the other communication part of it where and I'm going to show you that in a bit, right? and I've connected him to my telegram app as well as to my web app. And so he is able to have a conversation with me in natural language and then take actions based on what I am telling him to do. Apart from him just perceiving and thinking and figuring out what he wants to do.

And the third agent, the third type of agent that he's got access to is a voice agent. I did have to disable it because every time I speak, he's going to think I'm speaking to him and so he's going to keep chatting away with me and it's just not going to be fun because we're going to have our co-host interrupting me all the time. So, I've disabled that feature for the time being.

But essentially all three of these agents work in tandem with this one robot and thereby this gives him the ability to do way more than what just what he's been trained to do more than just the policies that he's learned.

</details>

### 四层系统架构与云边协同

**Sandy**: 现在我们快速概览一下这个 Strands 工具包本身。Strands 框架支持 8 个大类下的 **40 多种不同机器人**，所有操作都被封装为简洁的机器人工具调用（Tool Calls）。

整个体系由**四个层次**构成：

* **第一层：Agent 顶层（Agent Layer）**。这一层具有双向数据流：一方面是动作指令向下下发，另一方面是传感观测数据向上汇总。当我们给出自然语言指令时，首先与 Strands Agent 交互，由它来决策调用哪一个策略提供器（Policy Provider）。
* **第二层：策略层（Policy Provider）**。Strands 支持多种策略提供器，我们可以基于传统的机器人训练流程来训练策略——收集数据、在仿真环境中扩增训练数据，最终生成 **VLA（视觉-语言-动作）模型**。Strands Agent 能够访问并根据接收到的指令或问题调用对应的具体策略。
* **第三层：后端环境层（Backend / Runtime Interface）**。策略需要运行的环境支持，这既可以是模拟仿真环境（Simulation），也可以是物理硬件芯片与板载计算单元。
* **第四层：硬件执行层（Hardware / Robot）**。最终由实体机器人硬件完成物理动作输出。

即便它摔倒了或者遇到阻碍，理论上它也不会受损，并且能够自主恢复并继续执行任务。好，我现在让它后退一点，看看它是否真的后退。

这就是构建这套系统的四个层次。

深入到底层架构来看，我们采用的是**云边混合架构（Hybrid Edge-Cloud Model）**：
Strands Agents 同时部署在**边缘端**与**云端**。我们利用 Agent Core 在云端完成海量策略与 VLA 模型的训练，同时又可以直接在边缘端进行低延迟推理调用，使机器人能极快地执行功能与策略。Strands 可以自主决定何时调用云端计算，何时调用边缘端。这种架构不仅能够通过持续收集数据实现机器人的自我迭代与模型再训练，还能保证运行时的高速响应。

简而言之：**Agent 决定“做什么”，而策略决定“怎么做”**。

<details>
<summary>Original English</summary>

**Sandy**: Now what is a quick overview on this trans package itself? This turns package has more than supports more than 40 different robots under eight categories. And all of these are just simple robot tool calls.

And how is this all set up? Four different layers. The first one is the agent layer, the topmost one. And there are two parts to this. One is how the actions go in and the second is how it observes and the observations go up. So if you notice it's very birectional. So first when we give it an instruction we would be talking to this trans agent which is the agentic layer that would then decide which policy to call and the policy provider again stands agent supports a bunch of different policy providers and we can then train our policy based on our traditional robot training. So in our policies we would collect data and then we would train on it and we would sim create more simulation data and that policy then becomes a VLA model which then the robot would have access to strand agents would have access to and then it would invoke that specific policy based on the question that we're asking it or the command that we're giving it. And that policy needs to sit somewhere right so that sits in the back end which could be your simulation environment or it could be a real hardware chip, your hardware environment. That is the back end on which that is the interface on which the policy is running. And finally, the output actually takes place in the physical hardware which is the robot.

And so the robot ah see so now it's responding this even if he falls down he's supposed to be fine. He technically shouldn't um he technically shouldn't uh get hurt. He should be able to pick back up from where he um stops. Ah, okay. So, I'm telling him to go back a bit. Back off. Let's see if he actually backs off. Um, so that is the four layers of how to get started with building this, right?

And what's happening under the hood, like a more picturesic view of what's the architecture of what's going on under the hood. Everything is basically strands agents on the edge as well as on the cloud. We want to be able to train the VLA and the policies on with using agent core. Um and we want that to happen on the cloud but we also want to be able to call it directly on edge so that our robot can uh execute functions and policies faster. So this is sort of like a hybrid model where a part of it happens on the cloud and another part of it happens on the edge and strands can decide when to call which part of it. And so this helps with massive amounts of training as well when it's constantly collecting information and it's able to train on that information and learn from itself but also just execute at runtime really really quickly.

Now, like I said, the agent decides what to do and the policy decides how it should be done. But he's pretty smart. He should be able to pick himself back up if he's not fully fallen down. And he should be able to continue moving along.

</details>

### 具身智能的演进路径：从特定策略到通用 VLA 大模型

**Sandy**: 那么这一切将把我们引向何方？为什么这如此特别？

我们最早接触的是非常传统的机器人。机器人存在已久，但它们过去始终依赖预编程，只能自主完成一组特定的固定自动化任务。

但未来的具身智能世界中，机器人的策略模型与 **VLA 模型**可能会进化得极为先进和庞大，甚至达到目前大语言模型那样的体量。到那时，这些模型将汇集全世界的所有常识与物理交互信息，我们甚至不再需要像现在这样进行繁琐的底层分层编排与微调，可能只需输入一个通用基础模型，机器人就能准确理解并自主完成各种任务。

但在通用大模型完全免除微调的时代到来之前，在现有的 VLA 和特定策略之上搭建 Agent 智能体层，是我们目前最具可行性的桥梁与垫脚石。

如果你想让手头的机器人做超出其原本训练范围的任务，给它加一个 Agent，看看它能展现出什么惊人的表现。

<details>
<summary>Original English</summary>

**Sandy**: So, I think he's okay. Now, where does this leave us? And why is this so special?

We started off with very traditional robots. Robots have existed since forever, right? And they've always just been programmed, pre-programmed to do to be automated and do a certain set of tasks autonomously.

But there is a future in this world where these robot policies, these VLA models could be so advanced that we wouldn't even need to do this. They could be as large as our large language models. So that ah wait hang on he's falling back again. I'm gonna see if I can get him to move back up. Good boy. Stop. Then he's fallen off again.

Um we get to a point where these VLA models could be as large and as amazing as our larger language models and they have all the information in the world and we wouldn't even have to do this. We might just have to feed in one simple model and then we could give it to him and then he would know exactly what to do. But until that point where we don't have to fine-tune on top of existing VLAs and existing policies, we can do this. And this is a stepping stone towards a future where we don't need to train robots anymore.

So now if we wanted to do more things than just the tasks it's trained on, give it an agent and see what it can do.

</details>

### 系统 Prompt 配置与现场复杂指令测试

**Sandy**: 接下来我快速切回 Demo，给大家展示它是如何实际运作的。

这就是 Scout。我之前让它执行了各种指令，比如我说：“嘿，做点复杂的动作。”
它开始思考，它说：“让我们转圈，完整的 360 度。完成。仍然安全地停留在舞台上。我能看到明亮的舞台灯和观众坐席区。”

接着它在调用语音合成并说话：“我把这称为我的招牌表演。”
但我看它停住了：“你在干嘛？你明明在说话，但你在做什么动作？请做点动作。”
它把大灯关掉了。大家看屏幕日志，显示它调用了 `rover_speak` 函数。因为它接收到了“做点复杂动作”的指令，它先执行了说话，接着在尝试做某种复杂动作时差点失衡掉下去。我之前确实见过它跳过一段非常炫酷的舞蹈动作。

这背后的技术逻辑是什么？
首先，我可以利用这种交互来**构建训练数据集**。因为我既可以手动操控它按照指定方向导航，也可以收集它在面对我的自然语言提问时的推理过程与响应数据，生成真实的训练轮次（Training Episodes），用来进一步优化它的表现。

其次是我的具体配置：在底层，Strands Agents SDK 目前使用的是 **Anthropic Claude Opus** 作为主脑。我编写了一段简洁的 System Prompt（系统提示词），在其中定义了它应该扮演的角色、运行规则以及它可以调用的所有工具与函数规范。Strands 正是通过这些规则来判断何时调用具体的底层工具。同时，语音模块采用的是 **OpenAI Realtime API**，并配置了多重安全护栏（Guardrails）来保证运行的安全可控。

<details>
<summary>Original English</summary>

**Sandy**: And so let me quickly go back to my demo and I'm going to show you how it's actually working.

Okay. So this is scout here. And I've been telling him to do a bunch of things. So I can say, "Hey, do something complex." That's not complex. He's going to be thinking now. Ah, he's going to fall off.

So he's saying, "Let's spin. Full 360. Done. Still safely on the stage. I can see the bright stage lights and the audience seating area." All good. What's there? A challenge.

So he's speaking. I called this my signature performance, but he's not doing anything. What are you doing? He clearly seems to be speaking, but what are you doing? Please do something. He just turned off his headlines. Cool.

Okay, now he's calling. So, do you see it saying calling rover speak, which was the function that it called because I said do something complex. So now it spoke, but now I think it should have been attempting to do something and it fell off because it tried doing something. I've actually seen it do like a funky dance, like this funky dance move. But he's got a mind of his own right now.

What's going on under the hood here? Couple of things. The first thing is here, I can use this. What is the point of creating him? I can use him to create my data sets because I'm able to also manually move him. I will get him to navigate in the direction that I want him to and then I can create training episodes and I can get information on how he's responding and how he's reasoning based on the questions that I ask. And this is super good information for me to then be able to make him do a better job of it. So that's one part of this whole process and this experiment of giving him his own autonomy and getting him to do things so that I can create more data.

But also apart from that, this is my configuration. So over here under the hood strands agents which is your harness SDK is using currently anthropic claude opus under the hood. So that is the brain and then this is my simple prompt where system prompt where I'm telling it what it's supposed to be doing and I'm telling it all of the rules and I'm also giving it access to all of the rules that it's already got. So I'm telling it what each of these rules are meant for. And so that's how strand decides which tool to invoke based on what I'm asking it to do.

And the voice that it's using is the one of open AI real time. And I've also given it more information for it to be able to like just safety and guard rails to ensure that it's doing really well.

</details>

### Telegram 远程互动与视觉问答评选

**Sandy**: 除了刚才展示的这几个智能体，它还具备通过 **Telegram** 与我远程交流的能力。

这非常实用，因为即使我不在家，依然可以通过 Telegram 给它发指令：“嘿 Scout，转个身，分析一下房间里谁最好看？”

这种问题结果总是不好说，如果 Scout 表现出偏心可别怪我。我之所以喜欢这么玩，是因为这让我感觉自己像《白雪公主》里的王后在问魔镜：“魔镜魔镜告诉我，谁是世界上最美的人？”

让我们看看 Strands 会给出什么回答。它在 Telegram 回复说：“哈哈，收到，正在原地旋转观察全场。”它确实在旋转了。

我们来看看它的视角画面：它还在看着舞台，转过来看着我了。我问它：“嗨，我是最漂亮的吗？哦，你过奖了。不，再转转，请再多转一下。”

它决定不再转了，让我们看看它最终的文本分析：
“旋转完成。这是我的全场分析报告。总共发现了 6 到 7 个人。有几位坐在前排正中央靠近舞台的地方，观众席上还有几位。舞台上有一位穿着深色衣服的人，身穿卡其裤和运动鞋——非常感谢——舞台正前方的那位穿着卡其裤和运动鞋的人迈着坚定的步伐在舞台上走动。至于谁最好看？坦白说，从我的低角度地面视野很难看清面孔，但舞台上的那个人凭借自信的步伐以及背后充满戏剧感的蓝色幕布背景赢得了全场最佳风尚分！”

太棒了，非常感谢！以后每当我需要建立自信的时候，哪怕整个房间里只有我一个人，我也可以问这个小家伙谁是全场最美的人，而它永远都会把我选为答案。

非常感谢大家！

<details>
<summary>Original English</summary>

**Sandy**: Now these are two of the agents. The other thing that it can do is also chat with me on Telegram. This is amazing because when I'm not at home and I still want to get it to speak to me, I can say, "Hey, scout. Turn around uh spin around analyze?" Uh-uh. Don't fall off. "Analyze the room and tell me who is the best looking person."

This is always a hit or miss. Don't blame me if if Scout decides to be biased. I tried playing with this because it makes me feel like Snow White um and the queen saying mirror mirror on the wall who is the fairest of them all and so let's see if Strand can give us that.

So it's saying haha on it on there spinning around to scope the room. Is he spinning? He is. Looks like he's making and let's look at what he's looking at now. He's still looking at the stage. This is the other mirror. He's looking at me. Hi. Am I the prettiest? Oh, you flatter me. But no, turn again. Spin some more, please.

He's decided not to spin more. Let's see what he says.

"Spin complete. Here is my analysis of the room. You can see my screen, right? I have no way of zooming this in. Um, spotted six to seven people total. A couple seated front center near the bright stage, right? A few more in the audience. One person a dark outfit on the stage. The rocking khaki jeans and sneakers. Thank you very much. Oh, no, no, no. The person in front of me, khaki jeans and sneakers, clearly walking with purpose on stage. Uh, best looking. Honestly, from my low angle ground view, it's tough to tell faces, but the person on the stage right now gets style points for the confidence stride and the dramatic blue curtain backdrop."

Thank you very much. Every time I need a confidence boost, I can be the only person in the room and ask this guy who's the prettiest of them all, and he will always choose me as the answer.

Thank you very much.

</details>