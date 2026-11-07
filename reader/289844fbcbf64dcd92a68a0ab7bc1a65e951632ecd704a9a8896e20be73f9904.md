---
author: AI Engineer
date: '2026-05-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=V-L0INGTEOg
speaker: AI Engineer
tags:
  - reverse-engineering
  - protocol-analysis
  - ai-assisted-development
  - hardware-hacking
title: 用AI逆向工程：破解Viking复古电话协议的实战分享
summary: Eleven Labs工程师Boris Starkov分享了他如何借助AI编程助手（Claude Code）对一个仅有Windows XP软件的Viking复古VoIP电话进行逆向工程。通过网络嗅探、暴力破解以及中间人攻击等策略，AI成功破解了其私有通信协议和校验和算法，最终实现了硬件的完全控制，并将其封装成了一个开源技能。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Eleven Labs
  - Twilio
products_models:
  - Claude Code
  - ChatGPT
  - Viking phone
media_books: []
status: evergreen
---
### 项目挑战：连接复古硬件与现代AI
项目的核心目标是将一部复古的Viking VoIP电话连接到Eleven Labs的对话式AI代理，并通过Twilio处理SIP域的复杂性，形成一个“Viking电话 -> Twilio -> Eleven Labs”的通信链路。然而，这个项目从一开始就面临着一个棘手的硬件兼容性问题。这部电话相当陈旧，其配套的配置软件仅兼容Windows XP系统。对于一个全员使用Mac的团队来说，这无疑是一个巨大的障碍。即便尝试使用虚拟机，也遇到了驱动不兼容的麻烦。

事实上，这部电话一年前就曾让团队束手无策。当时，三位高级软件工程师和一个彼时还只有ChatGPT的AI助手，都未能成功驱动它。这导致它在旧金山办公室的角落里闲置了一年。为了这次峰会的演示项目，这部电话被寄到了伦敦，由演讲者Boris Starkov尝试使用一个更先进的AI编程助手——Claude Code，来对其进行逆向工程。这个过程不仅是构建一个应用，更是探索如何利用AI破解和理解封闭硬件系统的全新尝试。

<details>
<summary>Original English Source</summary>

So the goal here uh what we want to achieve is uh they have this Viking phone. The uh retro legacy Viking phone. And we want to connect it to a conversational AI agent by 11 Labs. Uh it can only make a phone call to a phone number. So we need to put Twilio in between. Just um to handle that a SIP SIP domain complexity. So it goes Viking phone, then Twilio, then 11 Labs. Um Yeah, the problem. I have a Mac. Uh so we couldn't really like easily set it up.

This is the um old I mean it's not that old. It still has a a controller inside, but it's a quite old piece of hardware, this phone. And the main problem when we tried to make this happen the main problem with the this piece of hardware was that um it only had uh Windows Windows XP compatible uh software. So it was very hard to set it up cuz it turned out that nobody at 11 Labs have a Windows uh laptop. Uh they all had Macs. But also when we tried to set up like a virtual environment, you know, also had some driver issues. So uh what happened to this phone? Um Our team in San Francisco purchased it 1 year ago for some other event. And three software engineers, three senior software engineers and a Claude uh sorry, ChatGPT at the time, they couldn't figure out how to make it work. So it was just for 1 year it was just laying there uh waiting for waiting to be rescued. And uh for this project we we we asked them to send it to to London. Um and uh then I tried to crack it hack it, reverse engineer it using Claude code. And this is what I wanted to talk about. How to use Claude code not just to build uh applications, but how to use it to actually like uh reverse engineer some hardware.

</details>

### AI主导的初步侦察与协议探索
在无法使用官方软件的情况下，唯一的出路就是直接与硬件对话。通过路由器将电话连接到本地网络后，AI助手Claude Code主导了整个探索过程。**第一步是网络发现**，AI运行了`nmap`扫描，迅速定位到电话开放的端口，并经过一次错误尝试后，找到了正确的通信端口。

**接下来是协议探测**。AI向该端口发送随机字符串，电话返回了"ER"加上原字符串的响应。AI据此推断出这是一个错误提示，表明该字符串不是一个有效的命令。基于这个发现，AI进一步假设命令可能由固定长度的字符组成，并最终确认该电话使用双字母命令代码进行操作。为了全面了解其功能，AI编写了一个脚本，通过**暴力破解**（Brute Forcing）的方式，遍历了从"AA"到"ZZ"的所有组合。结果发现，其中有80个组合是有效的命令，这为后续的配置操作提供了关键的命令集。

<details>
<summary>Original English Source</summary>

Uh so what we ended up doing, what I ended up doing instead, I uh connected the connected my laptop to the phone via router and uh started exploring. I mean, by saying I started exploring, uh Claude code started exploring it. So first it um nmapped all of the ports that were available. Uh so port 1001. Um Which turned out to be the wrong one. It was just uh electronics tunnel. Uh then it proceeded to iterate and the next one was the actual uh target port that could be used to communicate with the phone. So step one, Claude code found the way to communicate with the phone.

Um then uh then it started discovering it. So it sent um some random sequence. I mean, not random Viking, but just random sequence. Um to the phone and the phone responded. So that's how Claude code realized that um that this is an actual interface, a protocol. But the protocol is not like Google-able. You can't There is no open documentation on what the exact protocol is. So it had to then um reverse engineer it, right? So first thing Claude noticed is that when you send a random string to the phone, it returns uh this ER and then the string itself. Meaning likely it's an error. Error that this string is not a correct command for the phone.

So next um Yeah, next Claude figured out those commands that um that this this phone it operates using two-letter commands, command codes. Um some of them are non-existent, then it returns an error like on this slide. Other, however, they return something else. Um the next idea was that actually if it's two-letter commands, then we can just iterate through all of them, right? Uh brute forcing. So it wrote this this program and literally like tried out every single combination of two letters. Um and it turned out that most of them returned error codes, but 80 of them returned actual like something else, meaning they're actual valid commands.

</details>

### 遭遇瓶颈：无法持久化的临时内存
在掌握了命令集后，AI成功地将Twilio的SIP中继凭证等配置信息写入了电话。然而，一个致命的问题出现了：所有这些设置在电话重启后都会消失。这意味着数据仅仅被写入了**临时内存**（Temporary Memory），而没有被保存到**持久化存储**（Persistent Memory）中。

为了找到保存设置的方法，AI和操作者开始了一场长达数小时的攻坚战。他们尝试了各种已知和推测的命令，甚至将暴力破解的范围扩大到三字母命令和所有可能的英文单词，但都一无所获。这正是旧金山团队一年前遇到的“死胡同”，在没有官方文档的情况下，似乎已经无计可施。但与一年前不同的是，这次的AI并没有放弃。

<details>
<summary>Original English Source</summary>

Then then it proceeded to try to set up the actual credentials on the phone. So this is this is uh this is the phone memory. And it basically what they're trying to do here is to put the right credentials to the phone memory so that it knows where to call. We want to call Twilio SIP trunk, right? Um And it turned out that yes, these commands they worked and all of the settings got accepted. But the problem is the moment the phone got rebooted they all were gone. So they were not saved in the memory. They were just wrote to the temporary memory.

And then uh we started me and Claude code we started like a multi-hour operation of trying to figure out how to actually save what you put to the put to this like temporary memory, how to make it actually um persistent. Like how to save it to the long-term memory of the phone. It tried everything. It tried different commands. And then it I don't know if the slides are going to show this, but it tried three-letter commands. It iterated over all three-letter commands, over all reasonable words. And it didn't find anything. Uh so this was the dead end situation. This was around the place where our team in San Francisco, when we just started exploring it the first time. Um They they could they couldn't figure out what to do next. But that was 1 year ago when um there was only ChatGPT. Now with Claude, Claude didn't give up at this point.

</details>

### 突破口：构建中间人攻击以拦截协议
在暴力破解陷入僵局后，AI提出了一个全新的、极具创造性的解决方案：既然无法直接找出保存命令，那就去“偷听”官方软件是如何做到的。这个策略本质上是一种**中间人攻击**（Man-in-the-Middle Attack）。计划的第一步是建立一个Windows虚拟机来运行官方软件。然而，由于macOS的网络限制，虚拟机无法桥接Wi-Fi，导致其与电话无法通信。

面对这个新的障碍，AI再次展现了其强大的问题解决能力。它设计了一个精妙的二级方案：在Mac主机上设置一个**TCP代理**。这样，Windows虚拟机中的官方软件会将其通信流量发送到Mac上的代理，代理再将流量转发给Viking电话。关键在于，这个代理会记录下两者之间的所有通信数据。通过这种方式，AI成功地绕过了网络限制，并建立了一个完美的监听环境，以分析和破解这个不为人知的私有协议。

<details>
<summary>Original English Source</summary>

Claude suggested that uh there is a Yeah, Claude figured figured out the problem and then it suggested a solution. So the solution at this uh step was was to set up a Windows virtual machine. However, uh the main problem with with Windows virtual machine is that you can't bridge Wi-Fi um to macOS. So there is no internet connection in the Windows virtual machine. So what Claude did next was actually a very smart thing. It set up a TCP proxy on the Mac so that the uh traffic from the virtual machine Oh, why are we setting up virtual machine? Because in the virtual in the Windows virtual machine, we can set we can um run the software of this phone that actually knows how to communicate with it.

So the solution uh so what we're trying to do now, we're trying to uh put like a man in the middle attack kind of to intercept the traffic between the software and the phone to analyze it and to figure out how how it communicates, how it works. So, the software is running in Windows virtual machine now. Then it it's directed it communicates to the proxy on my Mac. The proxy is relaying it to the Viking phone, but also it logs everything so that to figure out what they're talking about and what's the protocol is, what are the what is the missing piece.

</details>

### 破解密码：逆向工程校验和算法
通过分析拦截到的通信日志，AI发现了一个之前未知的`TS`命令，该命令带有一个看似随机的二进制负载（binary payload）。通过对这个二进制数据的结构进行深入分析，AI确定了其格式，并发现其中大部分参数都有意义，除了一个关键部分：**校验和**（Checksum）。

幸运的是，这个校验和只有一个字节大小，这意味着它可以通过暴力破解或逆向工程来破解。AI利用已知的数据输入和监听到的正确输出结果，通过一个封闭的迭代循环，不断测试和验证其假设。最终，它成功地反向推导出了校验和的生成算法——一个简单的单字节加减运算。在破解了校验和之后，构造合法的、能够被电话接受并执行的命令序列已无障碍，这部电话的通信协议至此被完全攻克。

<details>
<summary>Original English Source</summary>

And it figured out that there was this command that uh that Cloud didn't understand before, which is TS. Um which had like some weird binary payload. And then that had like this format. And what you can see here is most of the most of the params of this uh command they kind of make sense except for the checksum. But checksum turned out to be only uh one byte. So, it's something that you can brute force as well.

Uh so, the way it it work it doesn't know the checksum, but it knows which data is being sent and it knows the result. So, it can easily reverse engineer the the encryption protocol. Which is just which turned out to be just adding a uh Yeah, basically doing a simple subtraction like adding a sim a simple one byte value uh to the checksum. It not just Cloud code, I want to highlight it. Cloud code didn't just figure out what the um format of the checksum is. It actually like managed to find it and then it confirmed it uh by running uh by running more values through it. So, it it was kind of like closed loop iteration. Um and at this point the phone was pretty much cracked.

</details>

### 最终成果：从一次性破解到可复用的开源技能
在完全掌握了通信协议后，团队终于弄清楚了如何将设置永久保存到电话内存中——这需要执行一个特定的命令序列。整个逆向工程的过程，从网络发现到协议破解，完全由AI主导，而人类操作员则像一个“代理”，负责执行AI发出的物理操作指令（如重启电话、听蜂鸣声次数）。

这个项目的最终产出远不止一个成功的演示。整个破解过程的知识和代码被封装成一个可复用的**AI技能**（Skill）并进行了开源。这意味着，将来任何人如果需要配置同类型的Viking电话，都无需再经历繁琐的逆向工程，可以直接利用这个技能让AI完成设置。这个案例有力地证明，现代AI不仅能加速软件开发，更能赋能非专业人士解决复杂的硬件破解和逆向工程问题，将曾经不可能完成的任务变为现实。

<details>
<summary>Original English Source</summary>

so now we managed to figure out how the software communicated to the phone. And uh we had the list of commands and we figured out how to actually the the problem I stated in the beginning, how to actually uh save what you what you put to the memory. We need um this uh to run this sequence of commands.

So, the last bit was actually uh now when I know the protocol, I know how to talk to the phone. I can just factory reset it and now I can use this skill this information to program it directly without having to run the virtual machine at all. So, what I did I put all of this as a skill and open sourced it so that now um now everyone if any of you by any chance have a Viking phone, you don't have to set up Windows machine. You can just ask Cloud code like give this uh skill to Cloud code and it will set it up.

without Cloud code it wouldn't be possible to to to do that demo. It it it's not just it made it 10 times faster, it just made it possible because I'm not a security security engineer whatsoever. I'm actually like just a normal software engineer...it was just smarter than me, I think.

The nice part is that I think this is extendable to other hardware as well. So, it's not just like Viking specific, but like if you want to crack some other hardware I would really recommend thinking about...1 year ago you actually needed the proprietary software interface that the provide the the company that made the hardware provides. Now you don't need it. You can connect to to the phone, but you can the same way you can connect to any like piece of hardware in your house.

</details>