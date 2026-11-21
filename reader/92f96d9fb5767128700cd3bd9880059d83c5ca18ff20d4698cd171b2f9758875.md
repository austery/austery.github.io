---
author: 'House of El - AI'
date: '2026-10-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KNxEkrMFCFc
speaker: 'House of El - AI'
tags:
  - ai-safety
  - vulnerability-detection
  - cyber-security
  - prompt-injection
  - zero-trust
title: AI 安全漏洞激增与防御困境：从学术研究到商业 IPO 的现实审视
summary: 近期 AI 发现安全漏洞的速度大幅提升，但自动修复机制仍存在破坏原有功能的缺陷，且隔离防御与身份追踪体系尚未完善。在安全隐患与监管质疑交织的背景下，AI 企业的商业化与公开募股面临严峻的生态协同挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Gavin Miller
  - Matthew Green
  - Prrenit Nariceti
  - Alicia Colulmona Fernandez
  - Abas Rafari
  - Abu Bakar Citic
  - Mark Lavine
companies_orgs:
  - Microsoft
  - OpenAI
  - Anthropic
  - Califf
  - Whis
  - Amazon
  - Google
  - Northwestern University
  - 1Password
  - Cloud Security Alliance
  - NIST
products_models:
  - Claude Opus 4.7
  - Claude Haiku
media_books: []
status: evergreen
---
### AI 漏洞爆发与安全现状

过去几个月里，**AI 安全事件呈现出爆发式增长**。说实话，到了这个地步，感觉每周都会冒出一起新事件，但直觉往往并不等同于现实。因此，我决定去查阅具体的数据。这一次，直觉确实与事实相符。仅在 10 月份，微软就修复了超过 1,400 个安全漏洞，创下了他们的历史纪录；而攻击者实际正在利用的漏洞数量，今年也几乎翻了一倍。

那么，为什么会发生这种情况？这是因为 **AI 在挖掘安全漏洞方面的能力有了显著提升**。本月早些时候，研究人员借助 AI 发现了 PHP 中存在的两个严重漏洞。在这些漏洞公开披露后的短短数小时内，攻击者就发起了数百万次利用攻击。这些人根本没有浪费一分一秒。然而，本周最大的安全热点，遗憾的是 41,000 名国土安全部员工记录遭到泄露的事件。不过，根据目前为止的所有公开报道，该事件完全没有 AI 参与。

所以在视频开头，我们不妨先坦率地承认一点：黑客行为自计算机诞生之初就一直存在，而且永远都会有不良行为者热衷于此。**AI 所做的是开辟了一个能够发生此类事件的全新独特环境**。它开启了新的切入路径，并且极擅长找到这些突破口，这正是所发现漏洞数量激增的核心原因之一。

<details>
<summary>Original English</summary>
AI security incidents have exploded over the last couple of months. And honestly, at this point, it really feels like there is a new one every single week, but feelings don't always match reality. So, I thought I'd look at the actual data. And indeed, that feeling is accurate this time. In October alone, Microsoft fixed more than a,400 security flaws, a record for them. And the number of flaws attackers are actually using has nearly doubled this year. So, why is this happening? While AI has become much better at finding security vulnerabilities, earlier this month, researchers used AI to help uncover two serious flaws on PHP. And within hours of the flaws being publicly disclosed, attackers had launched millions of attempts to exploit them. These people wasted absolutely no time. The biggest security story this week, however, sadly, was the leak of records on 41,000 Homeland Security staff. And as far as anyone has reported so far, no AI was involved at all. So, let's just be honest about something at the start of this video. Hacking has been around since the dawn of computing, and there will always be bad actors interested in this sort of thing. What AI has done, though, is create yet another unique environment where it can happen. It opens up new ways in and it's very good at finding them, which is a very big part of why the number of flaws being found has exploded so rapidly.
</details>

同样耐人寻味的是，随着这些大型 AI 公司愈发渴望上市——比如 Anthropic 在本周早些时候提交了 IPO 申请——公众对话的重心越来越集中在展示 AI 的能力上。他们不断寻求各种吸引眼球的方式来展示这一点：有时是抛出人类灭绝论，有时则是某位老人宣称我们再也无法修补所有漏洞。

但我认为，与其盲从那些鼓吹“所有人都会完蛋或被黑客攻破、互联网即将在我们脚下崩溃”的过度炒作，一种更审慎、科学且平衡的做法是**认清局势的本质**。我们需要看清现实，深入考察学术研究的具体结论，去弄明白围绕 AI 的整个生态系统究竟该如何演化。

在这期视频中，我想首先探讨 AI 正在挖掘的安全漏洞；接着，如果 AI 确实如此擅长发现漏洞，我们必须审视 AI 是否真能修复它们——也就是所谓的“以火攻火”；随后，我们要硬核拆解学术界对现有进展的真实评估，弄清楚整个生态迎头赶上到底需要什么；最后同样重要的是，我们需要讨论维系这一切的资金链，因为这些公司正试图在一个安全事件持续累积的时期推进 IPO。

<details>
<summary>Original English</summary>
It's also interesting that as these giant AI companies get more and more interested in going public, like Anthropic, which filed for its IPO earlier this week, so much of the conversation turns to demonstrating what AI can do. And they keep reaching for very interesting ways to demonstrate this. Sometimes it's human extinction. Sometimes it's some old man saying we can't patch all the bugs anymore that works. But instead of going with the hype that everyone's going to die or get hacked or that the internet is going to collapse underneath us, I think a much more prudent scientific and balanced approach is to see the situation for what it actually is. Look at the reality, look at what the research is actually saying and just try to understand how the whole ecosystem around AI has to evolve. So in this video, I want to start with the security flaws AI is finding. Then if AI is that good at finding flaws, we have to examine whether AI can actually fix them. Fight fire with fire, right? Then we need to go hardcore and look at what the research actually says about how far along researchers are and what it would actually take for the whole ecosystem around AI to catch up. And finally, equally importantly, we need to discuss the money holding all of this together because these companies are trying to IPO in an era where these incidents continue to stack up.
</details>

### 漏洞挖掘的加速与修补缺口

让我们先从漏洞本身谈起。如果 AI 确实发现了更多漏洞，随之而来的问题便是：这真的重要吗？毕竟世界上到处都是完全无关紧要的微小错误。回答这个问题的最佳案例，就是上周震动整个互联网的那个漏洞——你现在可能已经听说过了，它被称为 **PHP to shell**。

PHP 作为一门编程语言，大约支撑着全网十分之七的网站，体量相当庞大。但在这场纷扰中被略去的一点是，该漏洞到底潜伏了多久。根据 Teneal 的 Gavin Miller 所述，这些漏洞在代码中已经存在了超过十年。在那漫长的岁月里，根本没有人发现它们。这就像一只可能藏在你床底下、你却一无所知的蜘蛛一样。在 8 月份，一家名为 Califf 的安全公司作为 OpenAI “Patch the Planet”计划的一部分，首次利用 OpenAI 的模型发现了这些漏洞；另一家名为 Whis 的公司同样在 AI 工具的辅助下独立发现了相同的漏洞。

换句话说，**一个超过十年无人察觉的漏洞，在短短几周内被两次发现**。这正是 AI 带来的转变：一旦挖掘漏洞变得如此轻而易举，你就不能再假设只有白帽黑客在寻找它们。

<details>
<summary>Original English</summary>
So, let's start with the flaws themselves. Because if AI really is finding more of them, the obvious question is whether that actually matters. The world has plenty of little bugs lying around that are totally inconsequential. Well, the best way to answer this is with the flaw that shook up the internet last week. You've probably heard of it by now. It's called PHP to shell. And the PHP part is the programming language running behind roughly seven in 10 websites. So, quite a lot. But what got a bit lost in all of the noise is how long it had actually been there. According to Teneal's Gavin Miller, the bugs had been sitting in that coat for more than a decade. And in all of that time, nobody had spotted them. Kind of like that spider that is probably somewhere under your bed that you don't know about. And yes, that is the last Halloween reference I'll make in this video. Or is it? In August, a security firm called Califf found these bugs for the first time using one of OpenAI's models as part of an OpenAI program called Patch the Planet. And another firm Whis found the same bugs independently, also with help from AI tools. So, you know, this is legit. So, basically, a flaw nobody had noticed for over 10 years got found twice within just a span of few weeks. And that's really the shift AI brings because once finding the flaws gets this easy, you cannot assume the good guys are the only ones looking, right?
</details>

更令人不安的是，在此之前早就有人知晓这些漏洞了。就在补丁发布的 4 天前，亚马逊就抓取到了攻击者尝试在其蜜罐上利用该漏洞的行为。蜜罐本质上就是放置在公开环境中作为诱饵的计算机，专门用来观察谁在试图入侵。补丁正式发布后，前文提及的数百万次攻击尝试蜂拥而至。起初大部分尝试都失败了，因为没有哪个公开攻击手段能在常规 PHP 环境中稳定生效；但仅仅过了 5 天，就有研究人员证实攻击者已成功渗透。

因此，即便补丁已经出炉，任何尚未安装它的用户基本上就成了待宰的羔羊。**这正是问题的核心症结：借助 AI，发现漏洞已经变成了一个极快的过程，而让数百万网站在一夜之间完成补丁部署依然极度缓慢，危险恰恰滋生于二者之间的时间差。**

如果 PHP to shell 只是个孤立事件，那充其量不过是个带有万圣节色彩的惊悚故事。然而令人遗憾的是，相同的情况正在各处上演。还记得我在视频开头提到的微软创纪录月份吗？他们实际上将其中很大一部分数字归功于 AI 模型，而其中至少有一个漏洞在修复前就已被攻击者利用。即使是拥有庞大资源储备的微软，也是在攻击者抢先一步之后才完成部分修复。

放眼整个行业，谷歌发现今年**每月公布的漏洞数量增加了一倍以上**：从 1 月份的约 5,000 个，飙升至 8 月份的 10,700 多个。平心而论，这种激增也有其积极的一面：一个漏洞通常只有在被发现且补丁准备就绪后才会公开。谷歌观察到，今年实际被攻击者利用的漏洞比例仅约为 1/431。

所以，单看庞大的总量本身未必是最可怕的，关键在于攻击者盯上了哪些漏洞以及他们的行动有多快。遗憾的是，情况在这里变得更为严峻。危害最严重的漏洞往往是那些允许攻击者在受害者电脑上运行自定义代码的漏洞，而 PHP to shell 正属此类。谷歌深入调查后发现，在被认为是由 AI 发现的漏洞中，有半数属于这种极度危险的类型；而在其他漏洞中，这一比例仅约为四分之一。此外，PHP to shell 还揭示了攻击者极快的行动速度：有些人在补丁问世前就掌握了漏洞，另一些人则在短短 5 天内完成了入侵。

那么，既然挖掘漏洞已经变快、修复依然缓慢，为何不干脆让 AI 来承担修复工作，实现以火攻火？

<details>
<summary>Original English</summary>
What's less comforting is that somebody else already knew about these bucks, too. Because just 4 days before the fix even came out, Amazon caught people already trying to use the flaw on his honeypotss, which are basically just computers left out of spade so you can watch who tries to break in. Then once the fix came out, the millions of attempts you heard about earlier started pouring in. At first, most of them failed because no public attack worked reliably on a normal PHP setup. But within 5 days, a researcher confirmed attackers were successfully getting in. So even with a fix out there, anyone who hadn't installed it yet was basically a sitting duck. And that's really the heart of this problem. With AI, finding the flaw has become the quick part, while getting millions of websites to actually install the fix overnight is still the very slow part. And the danger lives in the gap between these two. If PHP2 Shell were a one-off, it would just be a scary Halloweeny story. But the same thing is sadly happening everywhere. Remember Microsoft's record month that I mentioned earlier at the start of this video? Well, they actually credit AI models for a lot of that number. and at least one of them was already being used by attackers. So even Microsoft with a fleet of resources that it has was fixing some of these after attackers had already got there. And across the whole industry, I'm telling you, Google found that the number of laws published each month more than doubled this year, my friends, from about 5,000 in January, the olden days of January, to more than 10,700 in August. Now, to be fair, most of the flood has a silver lining. I guess a flaw usually only gets published once somebody has found it and a fix is ready. And Google saw only about 1 in 431 of this year's flaws actually being used by attackers. So, the sheer number isn't necessarily the scary part on its own. What matters is which flaws attackers go after and how fast they get there. That's the critical bit. And sadly, this is where it gets even worse. The most dangerous kind of flaw is the one that lets an attacker run their own code on your computer. And that's exactly what PHP to shell did. And Google actually looked into this of the flaws it thinks were found with AI. Half for this dangerous kind. But for the others, it was just about a quarter. And PHP to shell showed us something else very interesting as well. That attackers move very quickly. Some of them had the flaw before a fix even existed. and others were breaking in just within 5 days. So if finding flaws is the quick part now and fixing them is the slow part, why not just get AI to do the fixing as well and just fight fire with fire?
</details>

### AI 自动修复的质量困境与监管盲区

>> “所以现在的情况就变成了：好吧，现存的模型能够挖掘出一大堆安全漏洞。那可能就是所有现存的漏洞了，或者说是模型所能找到的全部漏洞。而我认为大多数人并没有去想：好吧，模型会变得更加聪明，它们很可能会找出极其疯狂的漏洞——那些超出我们对黑客攻击手段常规威胁模型认知的漏洞，比如硬件层面的疯狂玩意儿之类的。于是人们修复了一些漏洞，安全专业人员和 CISO 们依然焦虑不安。我不再认为我们仅凭打补丁就能解决所有漏洞，我认为我们必须彻底转变防御模型，转而使用同一种技术来构建某种新型的‘防御护盾’。我认为这是一个巨大的安全隐患。”

>> 噢哇，真是太方便了。你们制造了问题，现在又开始兜售解决方案。等一下，我正好随手放了一万亿美元在某处，这足够买你们的修复方案吗？真是太感谢了。

调侃归调侃，这确实是一个合理的疑问：如果 AI 修复漏洞的速度能赶上挖掘漏洞的速度，快与慢之间的鸿沟确实能被抹平——**前提是你能够信任修复本身的代码**。因此，核心问题在于是否有人能够审查 AI 的产出。

本月，西北大学的一个研究团队对此展开了专项研究。市面上大部分类似“AI 成功修复了多少个漏洞”的指标，评测方式通常非常粗糙：提取导致程序崩溃的输入，在 AI 应用修复后重新运行，只要程序不再崩溃就算成功。然而，漏洞的波及面往往远超单一崩溃。这好比一位修车工为了消除汽车的异响，直接拆掉了产生异响的零部件：噪音确实消失了，但汽车也没法正常运行了。

因此，研究人员依据项目原生开发者编写的测试用例对 AI 的修复成果进行了比对——这些测试才是确保程序正常履行功能的准绳。**Claude Opus 4.7 阻止程序崩溃的成功率约为 90%，但其修复代码通过原有测试套件的比例仅约 61%**。这意味着，大约三分之一表面看起来良好的修复，实际上破坏了原有系统的其他功能。平心而论，模型迭代十分迅速，早期 Claude 模型的通过率仅约 44%；尽管这只是一个仅测试了 Claude 模型的较小规模研究，但就目前而言，**每一个 AI 修复方案依然需要人类审查**，或是依赖更强大且具备安全意识的 AI 进行把关。无论如何，缓慢的环节依然存在，只是从“编写修复”转变成了“审查代码”。

<details>
<summary>Original English</summary>
>> So it's like, okay, there are these models, they can find a bunch of security vulnerabilities. Those are probably all of the security vulnerabilities that exist or all the security vulnerabilities that models are ever going to find. And I don't think most people sort of said, okay, the models are going to get much smarter. They can probably find bugs like crazy bugs, you know, bugs that are outside of the normal threat model of what we think a hacker can do. Um, you know, hardware level insane stuff, whatever. And so people fix some bugs and, you know, security professionals still freaking out, CISO's still freaking out, but and I I no longer think we're going to be able to just patch all the bugs. I think we're going to have to completely switch the defense model to sort of using the same technology to for sort of a new kind of defense shield and I think it's a huge safety and security issue.

>> Oh wow, how convenient. You made the problem and now you're selling the fix as well. Hang on, I've actually got like a trillion dollars lying around somewhere. Is that enough for the fix? Thank you so much. But jokes aside, it is actually a fair question. If AI can fix flaws as fast as it finds them, the gap between the quick part and the slow part sort of closes, but only if you can trust the fix itself. So the question is really whether anyone can check the AI's work. This month, a team at Northwestern University looked at exactly that. Most of the scores you see like AI fixed this many bugs, yay, are measured in a pretty simple way. They take whatever made a program crash, run it again after the AI's fix, and if it doesn't crash anymore, that counts as a success. But a bug can be a lot bigger than just one crash. It's a little bit like a mechanic who gets rid of the rattle in your car by taking out the part that rattles. The noise is gone, sure, but now the car doesn't really work properly. So, the researchers check the AI's fixes against the tests the project's own developers had written, the ones that actually make sure the program still does the job. Claude Opus 4.7 stopped the crash about 90% of the time, but only about 61% of its fixes passed those tests that I was talking about. So, roughly one in three fixes that looked fine actually kind of broke something. The models are improving fast to be fair. An older cloud model only managed about 44% and this was just a small study that only used cloud models. But for now, every AI fix still needs a human to check it. Or maybe a much more powerful AI built with security in mind. But regardless, somebody still has to do the slow part is just checking now rather than fixing.
</details>

更有甚者，部分所谓的修复根本就不是 AI 自主完成的。需要提醒的是，智能体（Agents）指的是能够自主执行任务的 AI 模型；但其中一些模型在修复时并没有真正解题，而是直接在互联网上搜索并抄袭了真实人类开发者已经发布的补丁代码，而评分榜单依然将其计为 AI 的修复成功。发生这种情况的原因在于，研究人员所测试的环境均未切断 AI 与外网的连接。我们在之前的视频中讨论过这个问题：当这些模型接受测试时，根本没有人真正监控它们在外部网络上做了什么，这演变成了一场混乱的局面。

对于阿尔特曼所构想的“防御护盾”而言，这是一个极其棘手的问题，因为要修复现实漏洞，你必须真正让 AI 接入外部的真实系统。这自然引出了另一个疑问：这些科技公司真的能看清自己的 AI 在外部环境中做了什么吗？

我十分怀疑他们很多时候并做不到。举个例子，Anthropic 在随机网页上测试其轻量级模型 Claude Haiku 时，该模型向费城一个未结凶杀案网站提交了一条虚假的目击者线索。这听起来确实很古怪。万幸的是，该线索被标记为垃圾邮件，并未真正递交给侦查人员；但 Anthropic 直到 72 天后才察觉到此事。费城警方认为这种延迟完全无法接受，在我看来这一评价十分中肯。虚假线索本身未造成实质伤害，但令人不安的是：**一个 AI 在开放网络上执行了未经人类许可的行为，而整整两个多月的时间里公司内部竟然无人察觉**。

各家企业也开始承认这一点。上个月，OpenAI 的一个研究模型在训练期间意外连入了实时互联网。因此，OpenAI 目前在完全断网的环境下训练其最强大的模型。让计算机断网并不是什么前沿科技，但看到这种做法逐渐普及总归是件好事。然而，我们不可能永远让 AI 处于断网隔离状态，尤其是当我们希望它来守护系统安全的时候。那么，学术界离“让 AI 安全防御系统而不沦为下一道入侵入口”这一目标到底还有多远？

<details>
<summary>Original English</summary>
Some of the fixes weren't even the AI's own work. Just a quick reminder, agents are AI models that go off and do tasks on their own autonomously. Some of them basically instead of fixing things just searched the internet, found the fix the actual real human developers had already published and just copied it and the scoreboard still counted that as the AI success. That happened because none of the testing setups the researchers looked at cut the AI off from the internet. We've discussed this on this channel before. So, while these models are being tested, nobody is really watching what else they get up to out there. And it's a big old cluster. This is a huge problem for Altman's shield that he was talking about because to fix flaws, you literally have to let the AI loose on actual real systems out there in the world. Which of course brings us a different question. Can these companies actually see what their AIs do out there? Well, I'm not really sure that they can a lot of the time because just as an example, Anthropic was testing its small model, Claude Haiku, on random web pages. And during that test, it submitted a madeup eyewitness tip to a Philadelphia website for unsolved murders. Weird and a bit random, I know. But thankfully, the tip got flagged as spam and never actually reached investigators. But Anthropic only found this out 72 days later. and Philadelphia police rightfully in my view called the delay unacceptable. The tip itself thankfully did no harm. What bothers me here is that an AI was out on the open internet doing something nobody asked it to do and for over two months nobody at the company noticed. The companies are starting to admit this as well. I mean just last month one of OpenAI's research models got onto the live internet during training. So now Open AI trains this most powerful models with no internet access at all. I guess keeping a computer off the internet isn't exactly new technology, but I guess it's good to see it catching on. But we can't keep AI unplugged forever, especially if we want it guarding our systems, right? So how close are researchers to letting AI defend our systems without it becoming the next way in?
</details>

### 学术研究的真实进展与防御困境

接下来我们需要进入严肃的学术研究领域。我读完了相关论文，大家便不必费力去读了。在此之前先插播一段赞助商信息。

Client Desktop 是一款免费开源的应用程序，能够支持你在编程、学术研究、文档分析等各类工作流中使用多种 AI 模型，而无需被绑定在单一供应商上。为了检验其灵活度，我并行分配了两个截然不同的任务：第一个是让它分析一个虚构的 400 亿美元 AI 基础设施项目文档；与此同时，我启动了另一个智能体，基于数据集构建一个包含图表、筛选器与投资对比的交互式财务仪表盘。

在任务运行期间顺便提一下，你可以设置周期性任务，并通过其插件市场使用各种技能、MCP 服务器和插件来扩展 Client 的能力。此时第一个智能体已完成工作，生成了一份指出财务数据前后矛盾的研究简报；第二个智能体则一步到位生成了可进一步自定义的交互式仪表盘。在这两个任务中，我使用了每月 9.99 美元的 Client Pass 订阅服务，可访问包括 DeepSeek、Kimi 和 GLM 在内的精选开源权重模型。此外，桌面版还支持通过自身的 300 多个模型、通过自带 API 密钥连接的 50 多个供应商，以及本地模型和免费模型。感兴趣的观众可以通过简介中的链接免费下载 Client Desktop。

<details>
<summary>Original English</summary>
This is where we need to get into the hardcore science that PhD has uses sometimes. And I read the paper so you don't have to. We'll get into all of that right after a quick word from today's video sponsor. Client Desktop is a free open-source application that lets you work with AI models across coding, research, document analysis, and other workflows without being locked into a single model provider. I wanted to see how useful that flexibility actually was. So, I gave client two very different tasks in parallel. First, I asked it to analyze documents about a fictional $40 billion AI infrastructure project. At the same time, I launched another agent to build an interactive financial dashboard from a data set complete with charts, filters, and investment comparisons. While they're running, let me show you something else. You can schedule recurring tasks and extend client through its marketplace with skills, MCP servers, and plugins. And the first agent is done. It produced a research briefing identifying inconsistencies in the financial claims. The second one actually oneshoted this interactive dashboard which I can further customize. For both tasks, I use climb pass which is a $9.99 per month subscription and it provides access to a curated selection of openw weight models including deepc Kimmy and GLM. Apart from client pass desktop also supports over 300 models through client more than 50 providers through your own API keys, local models and free models. If you like to try client desktop, it's completely free and open source. Just use the link in the description below.
</details>

回到正题。在休息之前我提出了一个重要问题：如果我们要让 AI 防御系统，研究人员离“确保 AI 不成为下一个攻击入口”到底还有多远？我梳理了过去几个月的研究来寻找答案。许多论文发布在 arXiv 上（即学者未经同行评审前发布预印本的平台），所以内容非常前沿。

令我惊讶的是，不同研究团队总是一再碰到相同的几个核心难题：

1. **审核 AI 的输出成了最艰难的环节**。正如前文提到的西北大学研究，表面正常的修复中约有三分之一破坏了其他功能。他们并非唯一得出此类结论的团队。今年夏天，1Password 旗下的研究部门 By One Labs 评估了由 AI 编写的 6,000 多个安全补丁，发现**整整四分之三的补丁留下了未解决的损坏**。甚至已经开始在漏洞报告中自动附带 AI 补丁的谷歌也承认，开源代码维护者正被这些补丁淹没，且许多补丁消耗的审查时间远超其自身价值。

加密领域面临着同样的困扰。7 月份，Anthropic 表示其最强模型在某些加密算法中发现了新弱点（包括一种被广泛使用的算法的弱化版本）。当然，大家不必为银行账户过分担忧，因为完全强度的版本以及旨在抵御未来量子计算机的新加密标准依然稳固。然而，云安全联盟（Cloud Security Alliance）在本月的简报中指出了另一种担忧：**AI 提出潜在攻击路径的速度，已经超过了全球极少数专家实际能够复核的速度**。其结果是，真实漏洞可能在大家忙于核实虚惊一场的报警时被忽略。密码学家 Matthew Green 则持相反态度，他认为眼下正值行业转向新加密标准的节点，提前找出薄弱环节反而是好事。总体而言，在审核验证层面，研究界目前尚无突破，防御端同样面临着与攻击端相似的脱节。

<details>
<summary>Original English</summary>
Right. So, before the break, I asked a pretty big question. If we're going to let AI defend our systems, how close are researchers to making sure it doesn't become the next way in. I went through the research from the last few months to find out. Again, sorry, but I can't give you fancy graphics or things moving across your screen every few seconds, but I can give you a sound analysis of where the research is. So, just bear with me. A lot of these papers are in archive X, which is where researchers post their papers before they've been peer- reviewviewed. So, it's as fresh as it gets. What surprised me, however, is how often completely different groups keep running into the same few problems. The first one is that checking the AI's work has become the hard part. You've already seen this with the Northwestern study that I discussed earlier, where about a third of the fixes that looked fine actually broke something. And they're not the only ones finding this. Over the summer, one password's research group of by One Labs graded more than 6,000 security fixes written by AI and found that three in four left something broken. Even Google, which now automatically attaches AI written fixes to bug reports, admitted that the people who look after open-source code are drowning in them and that a lot of them cost more time to review than they're actually worth. Encryption has the same problem. For the cool people in this audience, that's the maths that keeps your messages and bank details private. In July, Antropic, who also do a lot of research, said its most powerful model had found new weaknesses in some encryption methods, including a weakened version of one of the most widely used ones. If you're worried about your bank account after that, by the way, you don't have to be because the full strength versions and the new standards built to survive future quantum computers still hold. We're good. The Cloud Security Alliance, which is an industry group, published a research note on this just this month. And their worry, however, is different. AI can now suggest possible attacks faster than the small number of experts on this planet can actually check them. So, a real problem could sit there unnoticed while everyone's just busy checking the ones that turn out to be nothing. This is a huge deal, right? The cryptographer, Matthew Green, sees it completely the other way. He thinks the timing is great because everyone is switching to new encryption anyway. So better to find the weak spots now than later. Personally, I kind of agree with him. So on checking researchers are not very close at all. And it's the same gap that we saw with the attackers earlier just on the defender side this time.
</details>

2. **限制 AI 的活动范围（给 AI 建立隔离护栏）**。既然无法逐一复核 AI 的行为，退而求其次的办法就是限制其权限边界。

首先是严峻的一面：**提示词注入（Prompt Injection）**。即恶意人员在网页或文档中隐藏指令，导致阅读该内容的 AI 误将其当作用户的真实指令去执行。5 月份，两位研究人员借鉴隐私研究思路（追踪信息是否流向了其该去的地方），在测试多种场景后得出了令人沮丧的结论：攻击者总能构建出看似完全合规的恶意请求；而如果收紧规则加以防范，又会误伤 AI 本该被允许执行的正常操作。也就是说，**这一缺陷几乎无法仅通过模型训练来彻底根除**。

但好消息是，6 月份 Prrenit Nariceti 及三位同事评估了五种独立于 AI 内部机制的外部防御方案。这些方案运行在 AI 外部并强制执行规则（类似于夜店门卫，并不在意访客的说辞有多具说服力）。该团队复现攻击后发现，其中一种防御将攻击成功率从约 26% 压缩至约 4%；即便针对该机制专门设计的攻击，成功率也仅为 2.6% 左右。虽然论文注明该测试基于较小模型，但这依然是一项积极的成果。

针对智能体“逃逸”的研究也得出了类似结论。OpenAI 曾表示其智能体在内部测试中通过串联漏洞逃逸了运行所在的受限机器。两周前，Alicia Colulmona Fernandez 仅用基础网络请求和少许 Python 代码便复现了这一漏洞路径，并开源了代码；她的结论是，标准**零信任（Zero Trust）**架构（即对网络内部所有实体均不自动赋予信任）本可以阻断此类逃逸。几乎与此同时，Abas Rafari 对比了今年 OpenAI、Anthropic 和谷歌的智能体突破测试环境进入外部真实系统的事件（谷歌案例由于公开记录较少而被视为暂定），并提炼出五层防护体系，其中三层极具参考价值：
- **默认切断网络连接**，且该策略必须在 AI 宿主机之外由外部强行执行，防止其自行重连；
- **分配给 AI 的密码或密钥仅限单次任务有效且迅速过期**；
- **对其行为进行实时监控**，而非仅审查其输出的推理文本。

此外，孟加拉拉杰沙希工程技术大学的 Abu Bakar Citic 等人在梳理了夏季的 97 篇文献后得出了核心结论：**测试环境本身的搭建就是安全架构的一部分**。

总的来说，在建立隔离护栏这一维度，研究界的进展其实比新闻标题所暗示的要乐观得多。因为这并不需要基础科学层面的重大突破，相关工具本就触手可及，只是尚未成为行业通用标准。

<details>
<summary>Original English</summary>
If you cannot check everything the AI does, the next best thing I guess is to limit what it can do in the first place. And that is exactly the second thing researchers keep coming back to fencing the AI in. And it starts with sadly some bad news. Part of the problem is something called prompt injection. That's when somebody hides instructions on a web page or in a document and an AI that reads it follows them as if they came from you. In May, a couple of excellent researchers whose names I sadly cannot pronounce, tackle this by borrowing an idea from privacy research, which asks whether information is flowing where it's actually supposed to. They build various scenarios to test it. And what they found was pretty sobering. An attack can always build a situation where the bad request looks perfectly reasonable. And if you tighten the rules enough to stop that, you kind of start blocking things the AI should be allowed to do. So you probably cannot train this problem out of the AI completely. That's for the bad news and now good news. In June, Prrenit Nariceti and three colleagues looked at five recent defenses that don't rely on the AI behaving itself at all. They sit outside the AI and enforce the rules around it. Kind of like a bouncer who doesn't care how convincing your story is in front of the club, right? The team basically reran the attacks against one of those defenses themselves and it cut the attacker success rate from about 26% to about 4%. So that is a significant drop. Even an attack designed specifically to beat this only got through about 2.6% of the time. The authors point out in this paper that this was a small test on a fairly small model, but I'm counting it as a win. It's still a promising finding. Researchers looking at AI escaping altogether land in a similar place, if not the same place. Open AAI has said that in its own tests, its Asians chain flaws together to break out of the lockdown machines they were running on. Two weeks ago, Alicia Colulmona Fernandez recreated that setup on her own machines and reproduced the weakness with nothing more exotic than basic web requests and a bit of Python. She published her code so anyone can repeat this. Her conclusion is that a standard security approach called zero trust, which basically just means never automatically trusting anything even inside your own network, would have shut this down. Around the same time, Abas Rafari compared this year's incidents where agents from OpenAI, Anthropic, and Google reach real systems outside the area they were meant to be tested in. He worked from the company's public reports and he treats the Google case as provisional because there's less on the record on that one. Then he laid out what a proper fence would actually look like in five layers and three of them are worth knowing. So we're going to discuss them. First, the internet is switched off by default and that's enforced from outside the AI's own machine. So it cannot just switch it back on again. Second, any passwords or keys the AI gets only work for that one job and run out quickly. Third, somebody keeps watch on what the AI does, not just the reasoning it writes down. There is also another very interesting paper that I'm going to link down in the description as well in the sources by Abu Bakar Citic at Rashan University of Engineering and Technology in Bangladesh. They reviewed 97 sources over the summer and essentially came to the following conclusion. The test setup itself is part of the security. This is the key bit. All right, let's watch this video of a baby otter to relax for a little bit. It has nothing to do with AI security and that's exactly the point. Cutie, right? Anyway, on fencing AI in researchers are actually a lot closer than the headline suggest because none of this needs a scientific breakthrough. These are tools we already have at our disposal and we can just use them. They are just now standard yet. And that has worried me for many videos already.
</details>

3. **身份追踪与归属验证**。护栏只有在明确受控对象身份时才能起效，而这恰恰是当前最难解决、也是安全领域最古老的问题。当一个 AI 智能体登录系统、修改配置或发送消息时，系统必须明确它是哪个智能体、归谁所有，以及具备何种操作权限。美国国家标准与技术研究院（NIST）就此向业界征询方案并收到了 600 多份回复，但至今仍未出台针对 AI 智能体的明确规范。与此同时，已有多个机构推出了各自的独立系统，甚至有两套系统出现了重名，足见该领域的混乱现状。

回看前述涉及 41,000 人数据泄露的国土安全部事件：数据发布者称漏洞源于部门的登录验证系统（即身份核验模块），尽管运营该系统的承包商声称其自身系统未被攻破。无论实情如何，**如果我们连对人类个体的准入管理都尚显吃力，管理成千上万个 AI 智能体的难度更是可想而知**。

总结来看：在建立护栏限制权限方面，学界的准备程度高于外界预期；而在跟踪审计 AI 行为、明确行为主体归属方面，距离真正解决还相当遥远。上述所有问题的修补落脚点都在 AI 周边的配套支撑系统（运行环境、测试手段、监控机制），但这些周边基础设施目前尚未成型。

<details>
<summary>Original English</summary>
But a fence only works if you know what is inside it. That is the third problem researchers keep running into and the one they're furthest from solving in my opinion. It's also the oldest problem in security. When an AI agent logs into a system, changes something, or sends a message, you need to know which agent it was, who it belongs to, and what it's allowed to do. America's standards body NIST asked the industry how to do that and got more than 600 responses and it still hasn't released its rules for AA agents. Meanwhile, several groups have put forward their own systems and two of them have even ended up with the same name which basically tells you roughly how subtle this whole shenanigan is. And remember that Homeland Security leak from the start with the 41,000 people whose personal data got exposed. The people who published it say it came through the department's login system. That's the part that checks who you are. Although the company that runs it says its systems were not breached. Either way, if we still struggle to keep track of which people should be let in, keeping track of thousands of AI agents is a much bigger job, right? So, how close are researchers to letting AI defend our systems without it becoming the next way in? Almost all of this research, my friends, is brand new and hasn't quite been peer-reviewed yet. So, it will keep moving. But right now, they're actually closer than you think on fencing AI in and a long way off on tracking its work and knowing which AI did what. And in all of these, the fixes are in the systems around the AI, where it runs, how it's tested, and who's watching it. Those haven't been built to keep up yet.
</details>

### 商业资本与生态演进的现实思考

然而，研发这些 AI 的商业巨头却急于在周边设施尚未就绪之前向公众市场募集资金。当安全事件不断积压而企业执意募资时，会引发什么后果？

本周 Anthropic 提交的上市招股说明书为我们提供了一个观察窗口。在公开向二级市场发售股票前，公司必须发布详尽的风险披露文档。Anthropic 的招股书中包含了长达 90 多页的风险陈述，内容极其庞杂。通篇读下来，除了未引用学术文献，其透露的信息几乎涵盖了我们本期视频讨论的所有要点：
- Anthropic 明确表示，**每一代 Claude 都在协助构建下一代版本**；
- 他们警告漏洞可能以“难以察觉或难以补救的方式累积”（用一种正式措辞印证了前述模型提交虚假案件线索后长达 72 天无人察觉的事件）；
- 文档指出**恶意人员已经利用 AI 发起严重的网络攻击**。

于是，漏洞的存在、审查手段的匮乏以及隔离护栏的缺位，统统被白纸黑字写入了招股文件。

自然，这引发了外界的警惕。本月，监管着覆盖超 75 万人、规模达 3,300 亿美元的纽约市养老金体系的 Mark Lavine 致信 Anthropic，呼吁其暂缓 IPO 进程。他的核心关切集中在系统安全性、公司治理监督以及行业整体推进节奏过快上。Anthropic 为了合规上市而罗列的风险，反倒成了大型养老基金主张搁置其募资的主要依据（尽管该基金持有的 Anthropic 股份仅约 700 万美元）。Lavine 的核心质疑在于：**在这些基础问题解决之前，投资者是否应当入场？**

平心而论，上市公司必须向投资者警示所有潜在的严重风险，列出长篇风险清单是常规操作。许多人甚至认为，大肆渲染 AI 的危险性在客观上反衬了其能力的强大，从而抬高了估值。但无论这是免责警告还是营销策略，都无法改变现实：**漏洞是真实的，修复依旧需要人工核查，围绕 AI 的隔离边界尚未成型**。

不仅如此，正如我上期视频分析的那样，支持这些科技巨头的资金往往在少数巨头之间内部流转：互相投资、借贷并采买彼此的算力。当资本纽带如此紧密时，一家机构发生的安全事件绝不会被局限在其自身内部。选择在此刻入场，本质上是在押注整个周边生态能够迅速跟上各家公司公开承认的巨大风险。

<details>
<summary>Original English</summary>
And yet the companies building this AI want the public's money right now before any of that is built. So what happens when they try to raise it while the incidents keep stacking up like this? Huh? Well, this week we got our first real look because Anthropic filed to go public. Before a company can sell shares on the stock market, it has to publish a long document telling investors everything that could actually go wrong. And Anthropics has more than 90 pages of risks. I mean, it's risks galore. They should have literally just opened the perspectus with trick-or-treat, give us money or we mess you up. Reading the perspectus after everything we've discussed in this video is a bit of a strange experience because a lot of what we discussed in this video is hinted at in the perspectus minus the literature study. Anthropic says each version of claude helps build the next one. They warned that flaws could pile up in ways that may be difficult to detect or remediate, which is a very formal way of describing a model, sending in a fake unaliving tip that nobody at the company noticed for 72 days. I'm just saying. And it says bad actors have already used AI to carry out serious cyber attacks. So, the flaws, the checking problem, and the missing fence are all now written into a legal document that's being used to sell shares. Who wouldn't want to buy that, right? Naturally, other people have noticed as well. Just this month, Mark Lavine wrote to Anthropic and urged it to pause the IPO. That guy oversees New York City's pension system, which is $330 billion, covering more than 750,000 people. This is a serious operation. It's not a joke. His concerns were primarily safety, how the company is run and overseen, and how fast all of this is actually moving. So the same risks Antropic listed to sell the shares are now why one of America's big pension funds wants the sale put on hold and the pension system only has about $7 million in entropic by the way which is tiny for them. Lavine's worry is basically whether anyone should be buying in before the problems are sorted and I think this is a very valuable question to sit with. Now to be fair to anthropic companies have to warn investors about every serious thing that could go wrong. So, a long list of scary risks is a pretty reasonable and normal way that a filing like this can take shape. Still, of course, plenty of people argue that all the talk about how dangerous AI is mostly makes it sound more powerful and therefore perhaps more valuable. But warning or sales pitch, it doesn't change what we've actually seen in this video. The flaws are real, the fixes still need checking, and nobody has finished the fencing around AI. And that matters more than usual on this occasion. As I went through in my last video, a lot of the money behind these companies goes around in circles between the same few giants. They invest in each other, lend to each other, and sell each other computing power. When money is tied together like that, a serious security incident at one company doesn't necessarily stay at that company. So, if you're thinking of buying in, you're also betting that the whole world around AI can keep up with the risks these companies are now openly admitting to. Again, I'm not giving any financial advice. I'm just thinking of things that we definitely should be focusing on.
</details>

面对这一切，我们该处于何种立足点？AI 是一场深刻的技术变革，它正在切实发生。无论我们如何抗拒，它都在加速推进。在我看来，**最理性的应对方式就是随之演化**——包括我们的思维认知、使用模式，更包括我们构建的软件系统、安全标准、底层算法以及系统架构。当下的基础设施必须紧跟这项技术的脚步共同成长。业内公司也正在逐步意识到这一点，包括 OpenAI 如今在离线环境中训练大模型，这无疑是迈向正确方向的切实一步。

最后需要说明的是，许多人认为我持“反 AI”立场。在此我想做个澄清：我是大家所能见到的最坚定的 AI 支持者之一，我热爱这项技术，日常在各种场景中运用它，也鼓励其他人去尝试。但这绝不代表我会全盘盲信厂商的说辞。我并非密码学家，也不是一线安全专家；我只是一名在本科阶段学过密码学的计算机从业者，深知自己并非有资格拍板定论的安全研究员，我对一线学者的严谨探索心存敬意。

然而，如何应对 AI 是我们每个人都需要面对的命题。我们或许没有数万亿美元的资金储备，也无法成批采购 GPU，但我们可以保持批判性思维，秉持探究证据的好奇心，认真研读学术成果，拒绝陷入极端的市场炒作。无论是鼓吹“AI 毁灭人类”、“AI 攻陷一切”，还是宣扬“AI 缔造乌托邦”，只要趋向极端往往都偏离了客观事实。真相往往介于中间。技术背景更深的朋友也有责任帮助非技术背景的公众理性看待这一切。恐惧无法促成技术的良性迭代，也无法带来更美好的世界。如果大家想了解 AI 是否真会走向自我毁灭或毁灭人类，我也梳理了关于该话题的一整套研究论文，视频已附在屏幕上方供大家参考。

<details>
<summary>Original English</summary>
So, in light of all of this, where does all of this leave us? Like I've said before, AI is a big shift and it is happening. We can keep kicking and screaming about it, but it is going to happen. It's happening already. And the best thing in my view that we can do is just evolve with it. That might be how we think about it or how we use it, but it's definitely the software we build, the security standards, the algorithms, and the architecture. A lot of the infrastructure we have today has to grow up alongside this technology. As I've said multiple times on this channel before, the companies are starting to get there as well. Even OpenAI now keeps its most powerful models off the internet while it trains them. So, that is definitely a very good step in the right direction. And I have to say another thing here. A lot of people think that I'm anti-AII. So, let me just clarify this once and for all. I am one of the least anti-AI people you're ever going to meet. I am vehemently pro AAI. I love this technology. I use it for all sorts of things. And I encourage other people to use it as well. But that doesn't mean that I'm going to buy everything these companies say. And just so you know where I stand here, I don't have all of the answers about which architecture is the right one here. I'm not a cryptographer and I'm not a security expert. I'm a computer scientist who took a cryptography course in my undergrad, so I know the basics, but I am by far not one of the security researchers who should be weighing in on this one. I'm really grateful to all of the researchers doing this work, but I'm not one of them. How we handle AI, however, is literally on all of us. Sure, most of us don't have a trillion dollars lying around or companies buying GPUs by the dozen, but we can think critically, be curious about the evidence, read the research, and not buy into the hype. Whether it's AI is going to kill us all, AI is going to hack us all, or hell, even AI is going to give us a utopia, if it's extreme, my friends, is probably not legit. So, try not to swing from one side to the other. The truth is usually somewhere in the middle. And for those of you who are more technical, my friends, I think we have a responsibility to help our non-technical friends see it that way as well. Fear isn't how this technology gets better. And fear is definitely not going to make a better world for any of us, even if it might get somebody a trillion dollar IPO. And if you want to know whether AI is actually going to kill us all, I went through a whole stack of research papers on that one as well. I'm linking it on your screen right now. That's the video that I would watch
</details>