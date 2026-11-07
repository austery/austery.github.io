---
author: AI Engineer
date: '2026-07-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5192csoTkVo
speaker: AI Engineer
tags:
  - mobile-agent-control
  - tmux-workflow
  - tailscale-security
title: Remoby：基于 Tmux 与 Tailscale 的移动端 AI 智能体远程掌控方案
summary: 演讲者 Connor Adams 推出了开源项目 Remoby。该工具针对在外出时监控与引导 AI 编码智能体（如 Claude Code）的强迫性痛点，通过将本地的 Tmux 终端映射至移动端 Progressive Web App (PWA)，保留了原生终端的定制工作流。Remoby 针对手机触控进行了手势缩放、窗格切换等优化，并在底层默认通过 Tailscale 建立安全的点对点连接，实现安全、高效的移动端多智能体开发监控。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Claude Code
media_books: []
status: evergreen
---
### 移动掌控的焦虑：主流 AI 智能体手机端协同方案的局限

在当今 AI 辅助开发时代，许多开发者在离开电脑后，往往会产生一种强迫性的焦虑感：正在运行的 AI **智能体**（Agent: 自动执行任务的 AI 代理）是否在正常工作？是否卡在了某个环节？是否需要人类介入进行方向引导？这种想要随时随地查看智能体状态的需求非常普遍，但在移动端实现这一过程却面临着诸多挑战。

目前市面上主要有几种方案，但它们都存在明显的局限性：
* **Happy**：这是一款第三方工具，虽然为 **Claude Code** 提供了精美的原生移动端应用，但它仅局限于 Claude Code 一款工具，且其数据必须通过其未知安全性的中继服务器进行转接，这给商业代码和系统安全带来了潜在的隐私泄露风险。
* **官方内置手动接管机制**：Claude Code 官方支持将当前会话传递给官方移动端应用，但这种方案需要每次人工进行手动接管，且无法兼容像 **Codex**、**Pi** 或其他自定义的 AI 智能体开发流。
* **传统 SSH 终端 App**：直接在手机上使用传统终端（如 Termius）来管理远程开发。这种方案的痛点在于配置极其繁琐，开发者不仅需要手动管理复杂的 SSH 密钥，而且在手机屏幕上缺乏触控优化，极难配合类似 **Tmux** 这样的本地多任务多窗格工作流。因此，在“掌控感”与“便利性”之间，目前的移动端掌控方案依然存在着一道巨大的鸿沟。

<details>
<summary>Original English Source</summary>

My name's Connor Adams and I'm here to present to you Remoby... Who here uses checks on their agents on their phone? Okay. Who here would like to but it doesn't. Okay, yeah. I'm always actually torn about whether or not it's a great idea or not. I'm thinking I'm out, you know, out and about. May might be some nice weather. Out with my friends and family and then I get this sort of compulsion to check on my agents. Are they working well? Do I need to steer them? Do they need me? And so rightly or wrongly, that there are plenty of apps for it. So, before I show you mine, why have I built one? Well, one because I've got AI psychosis, of course, and you just must build apps. But the thing I wanted didn't really exist. So, there's Claude, there's Happy, which does Claude code. And it's got a nice native mobile app. But it only works with Claude code. And also it has some relay server that I'm not sure I really trust. Fine. What other options do we have? Another Claude code option. Well, you can use the inbuilt thing and it will, you press a manual handoff and it will hand off your session to the mobile app. That's cool. But it means that you have to manually hand over and also it means that you can't use code X or something else. Or Pi. Or there's just what about just having a terminal app for your phone. And these are also good. The annoying things I find with it is like managing SSH keys and setting all that up. Also having touch controls and having it work with your existing workflows that you may have in something like tmux.

</details>

### 终端极客的效率美学：基于 Tmux 的多智能体并发工作流

对于倾向于使用终端而非重量级 IDE 的开发者来说，拥有一个便携且一致的远程开发环境至关重要。通过 SSH 接入远程开发机，不仅能保持本地环境的纯净，还能让所有个性化配置随处可用。在这个过程中，**Tmux**（Terminal Multiplexer: 终端复用器）作为窗口管理器，扮演了核心角色。

在建立这种心理防线后，具体的语言博弈与多任务协同如下：
在 Tmux 的支持下，开发者可以在单个屏幕上划分出多个窗格（Panes）和窗口（Windows），实现真正的多任务并行。例如，同时运行并监控四个不同的 AI 编码智能体（即所谓的 **Agent Maxing** 或 **Token Maxing**），实时观察它们各自的并发工作进度。不仅如此，Tmux 还可以进行深度的个性化定制：在底部状态栏集成 CPU 使用率等系统监控指标，甚至绑定复杂的自定义快捷键。
在实际开发流中，当 AI 智能体完成代码修改后，开发者可以直接在 Tmux 窗格中快速唤起 **LazyGit** 或自定义的 **Critique** 工具，用以滚屏查看详细的代码差异（Diff），并在提交代码前进行严格的审核。此外，如果遇到本地端口被占用（例如某个 AI 浏览器代理程序后台卡死导致开发服务器无法启动），Tmux 配合命令行工具也能让开发者瞬间精确定位并将其杀掉（Kill）。这种高度定制化的本地工作流虽然效率极高，但唯一的挑战就是如何原封不动地将其“投射”到移动设备上，而不需要改变任何现有的操作习惯。

<details>
<summary>Original English Source</summary>

Tmux users. Buddy? Only a couple and that was unsure face as well. Okay, so if we don't use tmux, that's fine. So, I used to be a big VS code man and then now I just maybe cuz I think it's cool, I use the terminal. But also it's nice because it's a portable setup and I can, I've got a remote dev machine I can SSH into it. It's got all my same stuff on it. So, before we get onto the mobile bit, I will just show you tmux. So, this is my terminal and why not have four different coding agents on there at the same time? And so, what tmux is is essentially like a window manager for your terminal, so you're able to have these panes like this and you're also able to have windows that you can switch between. You see the tabs along the bottom. But you can also like customize it. It's probably a bit hard to read on the screen, but I've got stuff in the bottom that says, "Oh, this is the CPU usage." And all this sort of stuff like I can press buttons and then I can see how the computer's going or whatever. CPU blah blah blah. And I can set up all custom key commands. So, for example, I press this and then how agent maxing, how token maxing you're feeling. Do you think you can manage 16? Probably not. Four, let's say, and then you just press that and then it does that. And I didn't know how to do any of this and I probably still don't cuz obviously I vibed it. It knows how to use tmux. So, you just have like a vision in your head like, "I want to be able to do this." And there are apparently other cool apps that people use, you know, like conductor and stuff and I think it's all great, but at this moment, as Mari said, the the [__] around and find out stage, I'd rather sort of own what I'm doing and find my own workflows for now, but we'll see. And so that's a bit of tmux. A bit little bit more of tmux, actually. I should have called my talk tmux talk. But so, let's say I've done something on Claude code and it's done some work and then I want to see the diff. Well, I can load up lazy git in a window by just pressing some buttons and then I can scroll through it and I can see all my git stuff. Or there's other ones, there's a thing called critique and then I can scroll through the diff there cuz we're checking our code, of course, before we're committing it. And other like random things is like sometimes you have some random port being used and you're like, "Why isn't my dev server running? Oh, it's there's agent browser running on here. Let's kill it." And you can do that. And you can create all these little tools and create your own workflow. And then still not ship anything that users use anyway. But anyway, the point is you can customize stuff. So, that's that and then from there, I've got all my custom workflows that make me incredibly productive, of course. And then I'm like, "Okay, now I want to go and ruin my family time." Now I can do that.

</details>

### Remoby：触控手势与 Tailscale 安全防护的移动终端映射

**Remoby** 是一款为了彻底打破电脑与手机界限而诞生的开源 Progressive Web App (PWA)。它在用户的本地机器上运行一个服务端程序，并将其完全兼容于 iOS 和 Android 系统的浏览器或独立应用中。Remoby 的核心理念并不是让用户适应手机端的新工具，而是把用户现有的、极具生产力的 Tmux 终端工作流，原封不动地映射到手机屏幕上。

为了在小屏幕上提供良好的操控体验，具体的交互设计与手势优化如下：
* **手势缩放与滚屏**：支持双击某一个 Tmux 窗格以实现单窗格全屏放大/缩小的功能，并允许用户通过流畅的手势进行跨窗格滚屏浏览。
* **快捷触控控件**：在手机界面上提供了一排快捷触控按键，例如通过 Shift-Tab 快速将智能体切换至“计划模式”（Plan Mode），或者一键拉起 Git 提交日志与 Critique 差异对比视图。
* **自动化配置与安装**：Remoby 提供了自动化的 NPM 包和安装脚本。在运行安装时，系统会引导用户自动安装所需的 Tmux 辅助配置包，将这些触控手势与 Tmux 本地的快捷键绑定（Key Bindings）完美结合，几乎不需要手动编写配置文件。
* **安全通道（Default Tailscale Tunnel）**：由于 Remoby 需要跨越互联网进行数据传输，如果直接暴露在公网，本地开发机极易被黑客入侵。因此，Remoby 默认采用 **Tailscale** 建立加密的安全对等网络（P2P network），保障通信安全。当然，有经验的开发者也可以自行选择使用 Cloudflare Tunnels 或 Ngrok。这种在安全防护前提下实现的安全穿透，让开发者可以无后顾之忧地随时随地接管开发流程。

<details>
<summary>Original English Source</summary>

So, here's my phone and I can open up here. So, it's a progressive web app, so it works on iOS and Android and you're I'm running a server on my machine. And I press we've got a Pi version or we got This is the machine we're just in. And so that's where we were. We're exactly there and it's you can If I scroll back, oh it doesn't work. It usually shrinks, but it's cuz I'm switching. Anyway, and so I can do all that same stuff. So, say I need to put it into plan mode or whatever, there's a little shift tab thing here that I can switch it into plan mode. If I want to load up get, I've got a little thing for that. If I want to open up the critique thing, I can scroll. It's all got the just all the gesture stuff. And so if we look at this, it's not winning any design awards, right? It looks like [__] but you can actually it's I'd argue it's like it's minimally functional or or maybe functional. So, you can I've got like a touch So, you can like double click and it will zoom into each pane and then you can scroll on the panes or whatever as you please. There's nothing to scroll there. We can scroll on this one. So, you know, I can scroll on there or I can zoom in, zoom out. All that stuff. And so that's basically it. So, the idea is you have your workflow. You might like tmux and if you don't already, you might get into it. And then you can set it up. And talking of which, so yeah, it's an open source thing. I'll put a QR code. But it's called Remoby. And so you know what the best idea is? Is when you see a command that just runs a random shell script, you copy and you paste that into your terminal because you know it's going to lead to good results. And so, if you do this, you don't have to do that. It will guide you through it and it installs a skill that helps you set up tmux if you haven't got it already. Or if you've got tmux, it turns it into key bindings that you for your setup in the little touch screen mode on Remoby and it just helps you set up. But you can just install the skill and install the NPM package and have fun. And I think that's basically it. So, even if you're not going to do it, give us a few stars, would you, on the old GitHub? And I think that's it. Thank you very much. Yeah, you can. How how do you control tmux remotely? Is it just Is that Is that just a feature of tmux kind of that you're using? Yeah, yeah, so yeah, tmux is just the thing that makes it all like the panes and stuff. So, you're just jumping. So, when you set up Remoby, basically don't even have to think about it. It just calls tmux. And then you just like log straight into your session. So, you don't you don't really have to do anything. Yeah. A follow-up on his question, what's the communication between the phone... Is it just a website? I didn't touch on this at all, which is very very key point. So, yeah, it's just over the internet. But so I use Tailscale to do it, but you could use Cloudflare tunnels, ngrok, whatever you like. And security is your concern of that thing. Yeah, if you just put it on the public internet, you've pwned your computer. So. Is Tailscale the default process of setting that up? Yes, yeah, yeah, yeah. If not, I'd be a little worried. Yeah, it's the default thing. But yeah. All right. Thank you very much.

</details>