---
author: TED
date: '2026-06-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Kxw_e4bDxoQ
speaker: TED
tags:
  - autonomous-systems
  - drone-technology
  - public-safety
  - infrastructure-monitoring
  - computer-vision
title: 无形的天空基础设施：无人机如何重塑应急与基建
summary: 本演讲探讨了无人机技术如何超越军事用途，作为自动化基础设施在紧急响应和电网巡检中发挥革命性作用。通过软硬件结合的远程部署，无人机正在成为挽救生命和预防灾难的智能前线网络。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Adam Bry
  - Bilawal Sidhu
companies_orgs:
  - Skydio
  - American Electric Power
  - Zipline
  - Wing
products_models: []
media_books: []
status: evergreen
---
### 重塑对无人机的认知：从战场到后院

对许多人而言，无人机（Drone）是一个令人恐惧的概念。它往往让人联想到乌克兰或中东战场上的致命武器，在那些地方，无人机正以前所未有的规模制造着破坏与毁灭。乌克兰军方曾报告称，他们对俄罗斯军队造成的伤亡中有 96% 是通过无人机打击完成的。这是现代战场上令人胆寒的新现实，也是西方国家无法忽视的。

然而，我们今天需要探讨的是一种截然不同的无人机应用。这种应用离我们更近，并且已经产生了挽救生命的巨大影响。理解这一技术的最佳方式是直观的演示：操作者可以坐在温哥华的会场，通过一台笔记本电脑直接启动并控制一台位于太平洋彼岸（东京）的真实无人机。这种远程操作的实现，依赖于一种叫做**停机坪**（Dock）的设备。它包含大量先进技术，能将无人机转化为一个**完全自动化的、由软件定义**的设备。操作者无需亲临现场，软件系统就能确保飞行安全，甚至能够实现脱手状态下的自动追踪功能。

<details>
<summary>Original English Source</summary>
My guess is, for many of you, [a] drone is a scary concept. It might evoke images of weapons in Ukraine, in the skies over the Middle East, where these things are creating damage and devastation at a massive scale. Ukrainians reported last month [that] 96 percent of the casualties they inflicted on Russian forces were done via drone strikes. Now this is a terrifying new reality on the battlefield. It's also one that we can't afford to ignore in the West. But I want to use my time today to talk about an entirely different kind of drone use, much closer to home, that's already having life-saving impact. And I think the best way to understand it is just to show it to you. So I'm going to demonstrate the robotics technology live here on stage, sort of. So we are over here in Vancouver. Hi, TED. But I am connected to a drone in Tokyo. I’m going to click the launch button -- this is all live -- and a real drone is going to launch itself on the other side of the Pacific, and I can just control it right here from my laptop. So it's a little bit like playing a video game. But I can fly around, I can look and see whatever I want to see. So the thing that allowed me to do this is called a dock. So this is the dock here. It looks like kind of an intergalactic grill. (Laughter) So it's got a bunch of advanced technology in it, but it turns the drone into a fully autonomous device. It can be flown remotely. I don't need a person on scene, and it turns the drone into a software-defined thing. So I can fly it here, and the software will keep me safe. So I can just cruise under this awning -- or over -- its choice. (Laughter) I can tap on an object that I might be interested in. Now the drone is flying itself. It's autonomously tracking that car. This is hands-off -- it’s a very powerful capability. So I'm going to stop this now and initiate an autonomous patrol of the area.
</details>

### 无人机作为急救员：空间优势与公共安全

这种自动化能力的真正价值，在于它改变了紧急情况的响应机制。以俄克拉荷马城警察局（Oklahoma City Police Department）为例，他们在全城部署了这种带有停机坪的无人机来响应突发事件。在一起报警中，一名火车司机恐慌地称可能在铁轨上撞到了人或物体。在地面上，要搜查这片难以进入的区域可能需要一个小时，但无人机在几秒钟内就抵达了现场。它们确认了伤者的精确位置，引导急救人员迅速介入，从而成功挽救了生命。

在旧金山，这项技术则展示了其在打击犯罪中的**非对称优势**。面对一起车辆盗窃案，警方无需立即展开危险的地面追车，而是从空中紧紧跟随嫌疑人。当嫌疑人停车、换上偷来的车牌并开始给车窗贴膜（这往往是连续作案的开端）时，警方对他的位置和动机了如指掌。他们随后派出了便衣警察和阻车钉，兵不血刃地将嫌疑人抓捕归案。这不仅保护了社区和警察的安全，甚至也保障了嫌疑人的安全。自部署这项技术以来，旧金山警方的犯罪率下降了 30%，汽车盗窃率下降了 40%。目前，**无人机作为急救员**（Drone as First Responder）的理念正在全美数百个机构中普及。未来，对于任何 911 报警，默认的预期将是无人机在几秒钟内率先抵达现场并提供关键情报。

<details>
<summary>Original English Source</summary>
So that's cool, but why does it actually matter? Well I'm going to share with you a couple of stories. The Oklahoma City Police Department has placed dock drones all over their city, and they’re using them to respond to emergencies. So in this instance, a train operator called 911 in a panic, afraid that he might have hit something or someone on the tracks. Now this is very difficult to access. On the ground, this is probably an hour search, but the drone got there in seconds. It was able to find that, unfortunately, there was somebody on the tracks, but because of the drone, they knew exactly where he was. They were able to guide in first responders, and they saved this guy's life. Another example. (Applause) This is from San Francisco. Very different application but same concept. Responding to a 911 incident. Here, there's a stolen vehicle. So they're able to follow the stolen vehicle from the air. They know exactly where he is. They know what he's doing. I don’t know about you -- when I steal a car, I like to steal a license plate to go along with it. So SFPD knew that this happened, but they never actually caught anybody in the act. With the drone, they're able to get this asymmetric advantage. So now he's got stolen plates. He’s going to put the plates on his vehicle. [He] conveniently holds it up so we can read it from the air. (Laughter) Any guesses as to what's happening now? Window tint. He’s got a stolen vehicle, stolen plates, [and] he’s tinting the windows. So this is the beginning of a crime spree. He's probably going to go off and steal a bunch more stuff, but the cops know exactly where he is, they know exactly what he's doing, so they roll a plainclothes unit out, roll spike strips -- he’s got flat tires, he can’t go very far -- [and] they take him into custody. So this is safer for everybody involved. It’s certainly safer for the community [and] also safer for the officers. Honestly, it's even safer for the suspect because they know exactly where he is and what he's doing. Since SFPD has implemented this technology, they’ve seen a 30 percent drop in crime, a 40 percent drop in auto theft -- I can’t say that I blame the auto thieves. I probably wouldn't want to steal a car either. And this concept of drone as first responder is taking off across the country. So it started with a few agencies. Hundreds of agencies are now using it. By the end of this year, it'll be thousands. And right now, about five percent of the US population lives within a two-minute flight of a Skydio drone to respond to an emergency. But there are 240 million 911 calls every year in the US. And we're building towards a future where the default expectation for every emergency is that a drone shows up in a few seconds to provide targeted information [and] get better outcomes for everybody.
</details>

### 数字图景监控：从被动补救到主动预防

在公共安全之外，无人机也在重塑传统基础设施的运维方式。**美国电力公司**（American Electric Power）在其变电站中安装了无人机停机坪，用于执行主动和被动的巡检。在一次常规飞行中，无人机发现了一根配电杆出现了短路和起火的迹象——这是通过传统方式极难察觉的隐患。由于及时获取了无人机传回的精准画面，维修团队得以迅速介入处理。

要知道，美国历史上一些最具破坏性的火灾正是由电网故障引发的。无人机为我们提供了一幅完整的电网**数字化图景**（Digital Picture），将应对灾难的方式从被动救火转向了主动预防。同时，Zipline 和 Wing 等公司也在利用同样的自动化理念，推动日常物流配送（如外卖投递）的普及。在天空中部署这些“飞行摄像机”以获取高维信息，正在产生不可估量的价值。

<details>
<summary>Original English Source</summary>
That's one example. I’m going to show you a different category of use, though. We have energy utility customers that are installing these in their substations. So this is American Electric Power in Ohio. They've got a great pioneering program. They have the dock in the substation. They can use it to perform both proactive and reactive inspections. And on one of those flights, they spotted this. This is a distribution pole with signs of a short and a fire that they wouldn't have caught any other way. So thanks to the drone footage, they knew exactly where it was. They went in, they repaired it. Why does this matter? Well some of the most devastating fires that we’ve had in the US have been the result of energy utility faults -- where something breaks, something goes wrong, there's a short, it starts a fire. Drones enable us to have a complete digital picture of the grid to prevent this kind of thing from happening. And if it does happen, we can know about it sooner and faster and mitigate the response. So flying cameras all over the place to get better information is super impactful. But the same kind of concept applies to drone delivery. So companies like Zipline and Wing are using dock drones to make it safer and faster to get a burrito delivered to your doorstep. (Laughter)
</details>

### 机器视觉与智能底座：全天候运行的天空基建

支撑这一切运作的，是一座隐形的“技术大山”。无人机看似小巧，但其底层的技术复杂性其实与自动驾驶汽车和火箭不相上下。除了需要克服震动、热力学和空气动力学的挑战，最核心的技术突破在于**视觉系统**（Eyesight）——赋予无人机像人类一样观察世界的能力。现代无人机内置了强大的计算系统和**深度神经网络**（Deep Neural Networks: 模拟人类生物神经网络运作方式的 AI 算法架构），这使得它们能够像人类一样看世界，识别物体的位置和属性，并据此做出智能决策。

通过集成机器视觉与人工智能，无人机在完成自主巡检后，可以准确识别降落点并自动归位停机坪充电。从某种意义上说，自动化停机坪将无人机变成了一种类似云服务器的设备：它们能在后台持续不断地全天候（24/7）自动运行，为我们完成繁重且重要的工作。在 20 世纪，人类建造了交通、电力和通信基础设施；而在当今时代，这种动态的、智能的无人机网络不仅将重塑我们运维这些传统设施的方式，其本身也正在进化成一种无处不在的新型**基础设施**（Infrastructure）。这项技术虽然如同许多现代科技一样具有双用途的性质，但只要我们通过公共讨论凝聚共识，就能充分释放它服务社会的巨大潜能。

<details>
<summary>Original English Source</summary>
So there is a mountain of technology under the hood that makes this stuff work. Drones are deceptively small, but they're actually on par with self-driving cars and rocket ships in terms of the technical complexity it takes to make them work. There's vibration and thermals and aerodynamics, and the hardest part is making all this stuff work reliably when and where you need it. But the key enabling technology is actually eyesight -- giving drones the same ability that people have to look out and see the world. Our drones have very powerful computers built in that parallel our brains. They've got deep neural networks that parallel our biological neural networks. And the output is very similar to how humans see the world. They know where things are. They know what they are, and they can use all of that information to make intelligent decisions. So you might have noticed that I left a drone flying in Japan. We should go ahead and check in on that. This drone is performing an autonomous inspection. So this is a water tower that's in the area. I’m going to somewhat rudely interrupt it here. I click stop. I click return and land and dock. So it will now go back up [and] autonomously find its way back to the dock. Dock opens up. It uses vision and AI to detect its landing spot, and it will come in and do an automated landing. So the dock, in some ways, turns the drone into something like a cloud server, where these things can be running autonomously, continuously in the background and doing useful work on our behalf. So what did we actually accomplish with this mission? On an autonomous patrol like this, we can inspect the infrastructure, we can look for intruders -- looks like we might have caught somebody here -- and generally have a complete digital picture of everything that's happening. In the 20th century, we built transportation infrastructure. We built power infrastructure. We built communication infrastructure. And I think drones have the potential to fundamentally advance and transform how we operate all of this infrastructure. But I actually think infrastructure is a pretty good way to describe what the drones themselves are becoming. These things are dynamic, they’re intelligent, and they can run in the background, doing useful work for us constantly, 24/7. This is a future that we're incredibly excited to build at Skydio. Thank you. (Applause) Bilawal Sidhu: Hey, I'm Bilawal, the tech curator for TED 2026. Hopefully you enjoyed that conversation. Look, drones can be scary -- we see them on the battlefields of Ukraine. We also see them as toys and tools of entertainment. But there’s actually a very useful function for this technology: to go where people can’t, or go faster to a place before people get there. And that's this whole idea about drone as first responder and drone as like, essentially infrastructure monitoring. We had these crazy fires in LA that could have been prevented if we had drones that were surveying power lines and infrastructure that clearly, you know, caused that blaze. But again, like most things, this technology is very dual-use. And that's why we want to have these conversations. You ought to know about what the technology is capable of, how it’s being used in every facet of society, so we can have the discussion about what we want to do with it. I hope you enjoyed.
</details>