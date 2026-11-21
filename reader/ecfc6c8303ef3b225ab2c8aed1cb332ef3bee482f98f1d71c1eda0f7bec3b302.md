---
author: TED
date: '2026-11-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0-C6SKjKek4
speaker: TED
tags:
  - robotics
  - motion-control
  - computer-vision
  - motion-generation
title: 如何教机器人跳舞：从仿真模拟到动作编排工具
summary: 机器人娱乐初创公司 UFB 的 David Dobáš 展示了通过直接身体控制与动作模型训练机器人的方法。团队从原本在仿真环境中耗时从零训练单个动作，转向利用大量动作数据训练单一模型，使用户只需拍摄一段视频即可快速生成机器人动作并像剪辑视频一样完成动作编排。UFB 宣布在官网公开发布该套工具。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - David Dobáš
  - Bilawal Sidhu
  - Emerson
  - Johnny
companies_orgs:
  - UFB
  - TED
products_models: []
media_books: []
status: evergreen
---
### 直接身体控制与仿真训练

**David Dobáš**: 那么你想尝试点酷炫的东西吗，Bilawal？
<details><summary>Original English</summary>
David Dobáš: So you want to try
something cool, Bilawal?
</details>

**Bilawal Sidhu**: 太想了！我随时准备给你当小白鼠。你今天有什么想法？
<details><summary>Original English</summary>
Bilawal Sidhu: Hell, yeah!
I'm ready to be your guinea pig.
What have you got in mind today?
</details>

**DD**: 那就站到这个摄像头前面。试着打一拳。
<details><summary>Original English</summary>
DD: So stand in front of this camera.
And try throwing a punch.
</details>

**BS**: 好的。
<details><summary>Original English</summary>
BS: OK.
</details>

**DD**: 再来一拳。开始。
<details><summary>Original English</summary>
DD: Do another one. Go.
</details>

**BS**: 我能踢一脚吗？这显然就是你们做机器人格斗的方式。你能向观众解释一下这里发生了什么吗？
<details><summary>Original English</summary>
BS: Can I do a kick?
This is clearly
how you do your robot fighting.
Can you explain to the audience
what’s going on here?
</details>

**DD**: 好的。这被称为直接身体控制。这个摄像头拍摄你的视频，然后估算你做了什么动作，比如出拳和踢腿。接着机器人就会接受训练去做出类似的动作。
<details><summary>Original English</summary>
DD: Yeah. So this is called
direct body control.
This camera takes a video of you
and then estimates what motions you did,
like punches and kicks.
And then the robots
are trained to do similar motions.
</details>

**BS**: 你刚才说“训练去做类似的动作”。你实际上是怎么训练这些机器人做新动作的呢？
<details><summary>Original English</summary>
BS: You said
“trained to do similar motions.”
How do you actually train
these robots to do new motions?
</details>

**DD**: 好的。我在 UFB 工作，这是一家机器人娱乐初创公司。我的目标是教机器人做新动作，比如跳舞、出拳、搞笑动作。所以我通常会把成千上万个机器人放入仿真环境中。它看起来就像这样。然后发生的第一件事是，机器人们甚至不知道如何保持自身平衡，对吧？它们就像婴儿一样。你必须从零开始教它们，但你必须坚持下去。于是你继续训练。看着它们自我改进真的很有趣。随着时间的推移，它们会变得有点摇晃，但开始能够保持平衡了。如果你训练得足够长，它们基本上就能完美地掌握这个动作。
<details><summary>Original English</summary>
DD: Yeah. So I work at UFB,
[a] robotics entertainment startup.
So my goal is to teach robots new moves,
like dances, punches, funny moves.
So what I would do,
I would take thousands of robots
and put them in simulation.
So that looks like this.
And then the first thing [that] happens,
the robots don't even know
how to balance themselves, right?
They're like babies.
You have to teach them from scratch,
but you have to keep going.
So you continue training.
It's really fun watching them
improve themselves.
Over time, they get a bit wobbly,
but start, you know, balancing.
And if you train long enough,
they basically learn the motion perfectly.
</details>

### 克服仿真到现实的差距

**BS**: 我太喜欢这个了。所以经过数千次迭代后，机器人可以在仿真环境中做到了。现在显而易见的问题是，如果它能在仿真中做到，那它能在现实中做到吗？
<details><summary>Original English</summary>
BS: I love that.
So thousands of iterations later,
the robot can do it in simulation.
Now obviously the question is
if it can do it in simulation,
can it do it in reality?
</details>

**DD**: 那我来给你看个例子。这是我在教一个机器人为中国新年表演跳舞。正如你所看到的，这确实相当困难。

（笑声）

但这一次，他能成功的。他能成功的。
<details><summary>Original English</summary>
DD: Well let me show you an example.
So this is me teaching a robot
to dance for [a]
Chinese New Year performance.
And yeah, it's quite difficult
as you can see.
(Laughter)
But this time, he's going to make it.
He's going to make it.
</details>

**BS**: 看起来他掌握了。啊！

（笑声）
<details><summary>Original English</summary>
BS: Seems like he's got it.
Ah!
(Laughter)
</details>

**DD**: 是的，没成功。确实如此。所以即使它在仿真中看起来非常棒，你仍然必须花一些时间在实体机器人身上，以确保它能在真实的物理世界中工作。
<details><summary>Original English</summary>
DD: Yeah. Didn't make it.
But yeah. So even if it looks
really great in simulation,
still you have to spend some time
with the real robot
to make sure that it works
in the real, physical world.
</details>

**BS**: 你正在努力克服所谓的从仿真到现实（sim-to-real）的差距。现在看来这显然需要大量的工作。
<details><summary>Original English</summary>
BS: You're trying to overcome
the so-called sim-to-real gap.
Now obviously this seems
like a lot of work.
</details>

### 从单独训练到通用动作模型

**DD**: 是的，而且过去确实需要做大量工作。但幸运的是情况正在发生改变，因为大家意识到，与其像我刚才展示的那样从零开始训练每一个动作，不如获取大量的动作数据、不同的动作，并训练一个单一的模型来完成所有不同类型的动作，这样不是更好吗？这改变了一切，因为这样你真的只需要拍摄一段自己的视频，几分钟之内，你就能看到机器人做那个动作会是什么样子，以及它在仿真中看起来如何。然后你就可以用实体机器人进行尝试了。
<details><summary>Original English</summary>
DD: Yeah, and it used to be a lot of work.
But luckily things are changing
because people realized that instead
of training each motion from scratch,
like as I showed you,
how about we rather take
a lot of motion data,
different motions,
and train one single model
to do all different types of motions?
And that changes everything
because then you can literally
just take a video of yourself,
and in a couple of minutes,
you can see how the robot
would look like doing that motion
and how it would look in simulation.
And then you can try [it]
with the real robot.
</details>

**BS**: 这真的很酷。所以现在你只需要拿一段视频片段，拖进你做的这个工具里，然后模型就会搞清楚如何让机器人做出正确的动作。你不需要经历那成千上万步的训练了。
<details><summary>Original English</summary>
BS: This is really cool.
So now you can just take a video clip,
drop it into this tool that you made,
and then the model figures out
how to get the robot to do the right move.
You don't need those thousands
of steps of training.
</details>

**DD**: 没错。关键就在这里。所以我们在这里教机器人一些新动作玩得很开心。这是我的同事 Emerson。这是我在教一些出拳动作。但这并没有结束，因为借助这些模型，你可以直接开始把动作组合在一起，创造出复杂的编舞。我们制作了这个工具，让它变得像剪辑视频一样简单。你拖放不同的动作，将它们组合在一起，就能得到一整套编舞。
<details><summary>Original English</summary>
DD: Exactly. That's the thing.
So we had a lot of fun here
teaching our robot some new moves.
This is my colleague Emerson.
This is me teaching some punches.
But it doesn't end here
because with these models,
you can just start
combining motions together
and create complex choreographies.
We made this tool which makes it
as easy as just video editing.
You drag and drop different motions,
combine them together,
and you get whole choreographies.
</details>

### 降低创作门槛与现场演示

**BS**: 我太喜欢这个了。所以现在突然之间，如果你想给你的机器人编舞，基本上只需拿上一堆视频片段，拖到这个时间轴上，就可以大显身手了。这对正在观看和收听的观众来说意味着什么呢？
<details><summary>Original English</summary>
BS: I love this. So now suddenly,
if you want to choreograph your robot,
you basically take a bunch of video clips,
drag it into this timeline,
and you're off to the races.
What does this mean for the folks
that are watching and listening?
</details>

**DD**: 这改变了谁能参与机器人创作，对吧？过去需要整个工程团队花费数周时间的事情，现在任何人只要有一个想法就能做到。可以是舞者、运动员、创意人士。也可以是你。我们在 UFB 不想把这据为己有。所以我在这里宣布，我们正在我们的网站上发布你们在这里看到的所有这些工具，供你们每一个人去尝试。我迫不及待地想看看你们会创造出什么。
<details><summary>Original English</summary>
DD: This changes who gets
to build with robots, right?
What took whole engineering teams
several weeks
now everyone can do just with an idea.
It can be dancers, athletes, creatives.
It can be you.
We at UFB, we don't want
to keep this for ourselves.
So I’m announcing here [that]
we are releasing all these tools
you have seen here
for every one of you to try
at our website.
And I can't wait to see
what you're going to build.
</details>

**BS**: 我想你给我们准备了一个小惊喜，正好用来展示利用这项能力你能做些什么。
<details><summary>Original English</summary>
BS: And I think you’ve got
a little treat for us
just to showcase what you can do
with this capability.
</details>

**DD**: 是的。我们所做的是，邀请了来自奥克兰的当地舞者 Johnny 来到我们的办公室，他教了机器人一些他的动作。作为送给 TED 的一份小礼物，我们现在把这段表演带到了这个舞台上进行现场展示。
<details><summary>Original English</summary>
DD: Yes.
So what we did, we invited local dancer
Johnny from Auckland to our office,
and he taught a robot some of his moves.
And as a little gift to TED,
we are bringing it live
on this stage right now.
</details>

**BS**: 我们开始吧，机器人跳舞。
<details><summary>Original English</summary>
BS: Let's go, robot dancing.
</details>

**DD**: 开始吧。

（掌声）

（欢快的音乐）

（掌声与欢呼声）
<details><summary>Original English</summary>
DD: Let's go.
(Applause)
(Upbeat music)
(Applause and cheers)
</details>