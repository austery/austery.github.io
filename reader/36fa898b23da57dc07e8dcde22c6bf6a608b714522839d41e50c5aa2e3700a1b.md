---
author: Veritasium
date: '2026-04-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=PPJ6NJkmDAo
speaker: Veritasium
tags:
  - contactless-payment-security
  - mobile-wallet-exploit
  - nfc-attacks
  - cybersecurity-vulnerabilities
title: iPhone支付漏洞：锁屏下盗取万元的NFC攻击全解析
summary: 本视频揭示了一种利用iPhone的Express Transit Mode和Visa卡在特定条件下绕过手机锁屏和支付验证，实现高达万元金额盗取的NFC攻击。视频详细演示了攻击过程，包括拦截通信、欺骗手机以为是交通支付、伪造低价值交易以及欺骗支付终端。专家解释了攻击背后的技术原理，涉及对称/非对称加密和RSA，并探讨了Apple和Visa在此漏洞上的责任推诿。最后，视频强调了该漏洞的现实风险和潜在解决方案，并推广了个人信息保护服务。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Ioana Boureanu
  - Tom Chothia
companies_orgs:
  - Apple
  - Visa
  - University of Surrey
products_models:
  - iPhone
  - Apple Pay
  - Proxmark
media_books: []
status: evergreen
---
### 引言：解锁iPhone盗取万元的挑战

**主持人**: 我在这里和 MKBHD (Marques Brownlee)，我们要尝试从他锁定的 iPhone 里盗取 10,000 美元。
<details>
<summary>Original English</summary>

**Host**: - I'm here with MKBHD,
and we're gonna try to steal
$10,000 from his locked iPhone.

</details>

**MKBHD**: 真的希望它不会成功。真的希望它不会成功。
<details>
<summary>Original English</summary>

**MKBHD**: - Really hope it doesn't work.
Really hope it doesn't work.

</details>

**主持人**: 我要你把手机放在这个设备上。
<details>
<summary>Original English</summary>

**Host**: - I'm gonna get you to put that phone down
on top of this device.

</details>

**MKBHD**: [Marques] 好的。
<details>
<summary>Original English</summary>

**MKBHD**: - [Marques] Okay.

</details>

**主持人**: 就把它放在那里。
<details>
<summary>Original English</summary>

**Host**: - Just put it down there.

</details>

**MKBHD**: 就放在，好吧。
<details>
<summary>Original English</summary>

**MKBHD**: - Just put it on like a, all right.

</details>

**主持人**: 我感觉我像个魔术师，但我就是-
<details>
<summary>Original English</summary>

**Host**: - I feel like I'm a bit of a magician,
but I'm like-

</details>

**MKBHD**: 是啊。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 我什么都没改，对吧？
<details>
<summary>Original English</summary>

**Host**: - I haven't changed anything, right?

</details>

**MKBHD**: 好的。是的。
<details>
<summary>Original English</summary>

**MKBHD**: - Okay. Yeah.

</details>

**主持人**: 它还锁着。
<details>
<summary>Original English</summary>

**Host**: - It's still locked.

</details>

**MKBHD**: 它锁着。
<details>
<summary>Original English</summary>

**MKBHD**: - It's locked.

</details>

**主持人**: 没别的了。
<details>
<summary>Original English</summary>

**Host**: - Nothing else.

</details>

**MKBHD**: 是啊。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 这只是一个普通的支付终端。
<details>
<summary>Original English</summary>

**Host**: - This is just a regular payment terminal.

</details>

**MKBHD**: 是的。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 没什么奇怪的。
<details>
<summary>Original English</summary>

**Host**: - Nothing weird about that.

</details>

**MKBHD**: 见过这些。
<details>
<summary>Original English</summary>

**MKBHD**: - Seen these.

</details>

### 首次尝试：5美元的初步测试

**主持人**: 我们先来个小的，比如 100。
不，也许 5 美元？
我们从这种金额开始-
<details>
<summary>Original English</summary>

**Host**: - And we'll start with a
little, like, maybe 100.
No, maybe $5?
Let's start with something like-

</details>

**MKBHD**: 是啊，五。五。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah, five. Five.

</details>

**主持人**: 从五开始。
<details>
<summary>Original English</summary>

**Host**: - Start with five.

</details>

**MKBHD**: 听起来不错。
<details>
<summary>Original English</summary>

**MKBHD**: - That sounds great.

</details>

**主持人**: 是的。五块钱。
你觉得我们会拿走，
我们能从你手机里拿走吗？
<details>
<summary>Original English</summary>

**Host**: - Yeah. Five bucks.
Do you think that we can take,
like, will we be able to
get this out of your phone?

</details>

**MKBHD**: 我希望不能，但我
感觉你可能会成功。
我们来看看。
<details>
<summary>Original English</summary>

**MKBHD**: - I hope not, but I
kinda feel like you will.
Let's see.

</details>

**主持人**: 那么，我现在要
在这个设备上收取 5 美元。
你的手机还是锁着的，对吧？
<details>
<summary>Original English</summary>

**Host**: - So, now I'm gonna
charge $5 on this device.
Your phone's still locked, right?

</details>

**MKBHD**: 滴。
<details>
<summary>Original English</summary>

**MKBHD**: - Yep.

</details>

**主持人**: 我什么都没做。
<details>
<summary>Original English</summary>

**Host**: - I haven't done anything.

</details>

**MKBHD**: 这就像大卫·布莱恩。
<details>
<summary>Original English</summary>

**MKBHD**: - It's like a David Blaine.

</details>

**Henry**: [Henry] 这就像是最极客版的大卫·布莱恩。
<details>
<summary>Original English</summary>

**Henry**: - [Henry] It's like the
nerdiest David Blaine.

</details>

**MKBHD**: 是的。(笑)
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah. (chuckles)

</details>

**主持人**: 太棒了，所以。
试着轻触一下。我们开始了。
(手机发出提示音)
<details>
<summary>Original English</summary>

**Host**: - Sweet, so.
Just try to tap. We'll go.
(phone chimes)

</details>

**MKBHD**: 我的手机上发生了什么？
批准了？哇，哇，批准了。
(硬币叮当声)
<details>
<summary>Original English</summary>

**MKBHD**: - What just happened on my phone?
Approved? Whoa, whoa, approved.
(coins clinking)

</details>

**MKBHD**: 所以，好的。
我听到你在轻触这个的时候，
我手机上有什么东西发生了。
<details>
<summary>Original English</summary>

**MKBHD**: - So, okay.
I heard something happen on my phone
while you tapped this on this.

</details>

**主持人**: 是的。
我们给你小票了。
<details>
<summary>Original English</summary>

**Host**: - Yes.
We got a little receipt for you.

</details>

**MKBHD**: 设备已验证信用卡，5 美元。
所以，我要看看我的手机。
啊，哦，我有一笔新的 5 美元账单。
而且是现在的时间戳。
我一点都不喜欢这样。
所以，这很令人担忧。
<details>
<summary>Original English</summary>

**MKBHD**: - Credit verified on device, $5.
So, I'm gonna check my phone.
Ah, oh, I have a new $5 charge.
And it's time stamped right now.
I don't like that at all.
So, that's concerning.

</details>

**MKBHD**: 哦，所以我的手机必须放在这个东西上？
<details>
<summary>Original English</summary>

**MKBHD**: - Oh, so my phone had to be on this thing?

</details>

**Henry**: [Henry] 是的。
<details>
<summary>Original English</summary>

**Henry**: - [Henry] Yes.

</details>

**MKBHD**: 必须放在这个东西上吗？
或者，像是靠近它，我猜？
<details>
<summary>Original English</summary>

**MKBHD**: - Did it have to be on this thing?
Or like, near it, I guess?

</details>

**主持人**: 这样，嗯，
我可以解释它是如何工作的-
<details>
<summary>Original English</summary>

**Host**: - So the way, well, I
could explain how it works-

</details>

**MKBHD**: 是啊。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 但也许在那之前，
5 美元，这不算多。
<details>
<summary>Original English</summary>

**Host**: - But maybe before that,
$5, it's not very much.

</details>

**MKBHD**: 是啊。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 我们要不要试着提高一点？
<details>
<summary>Original English</summary>

**Host**: - Do we want to try upping it a bit?

</details>

**MKBHD**: 我...
<details>
<summary>Original English</summary>

**MKBHD**: - I...

</details>

**主持人**: 我要输入一个
稍大一点的金额。
<details>
<summary>Original English</summary>

**Host**: - I'm gonna enter a
slightly larger amount.

</details>

**MKBHD**: 小心。小心那个。
小心，小心。
那有很多零。小心那个。
<details>
<summary>Original English</summary>

**MKBHD**: - Careful. Careful with that.
Careful, careful.
That's a lot of zeros. Careful with that.

</details>

**MKBHD**: 天哪。好的。
<details>
<summary>Original English</summary>

**MKBHD**: - Oh my God. Okay.

</details>

### 惊人结果：10000美元的成功盗窃

**主持人**: 你觉得可能吗？首先，10,000 美元。
<details>
<summary>Original English</summary>

**Host**: - Do you even think it's
possible? Firstly, $10,000.

</details>

**MKBHD**: 我的意思是，信用，信用额度
卡上的额度超过了。
我不知道 Apple
Pay 能否让你这么做。
<details>
<summary>Original English</summary>

**MKBHD**: - I mean, the credit, the limit
on the card is above that.
I don't know if Apple
Pay will let you do that.

</details>

**主持人**: 问题还在于，你
用这张卡花这么多钱
是不是习以为常？你知道吗？
<details>
<summary>Original English</summary>

**Host**: - The question is also
are you used to spending
this amount of money
on this card, you know?

</details>

**MKBHD**: 不用手机。
这是大屏幕活动。
<details>
<summary>Original English</summary>

**MKBHD**: - Not from my phone.
It's like a big screen activity.

</details>

**主持人**: 是啊。
<details>
<summary>Original English</summary>

**Host**: - Yeah.

</details>

**MKBHD**: 比如，10,000 美元的购买，
我得检查一切。
所以，是的，不。这很不寻常。
<details>
<summary>Original English</summary>

**MKBHD**: - Like, $10,000 purchase,
I gotta be checking everything.
So, yeah, no. This would be unusual.

</details>

**主持人**: 我们来看看。看看它是否有效。
好的，我再来一次。
<details>
<summary>Original English</summary>

**Host**: - Let's see it. Let's see if it works.
Okay, I'm gonna do it again.

</details>

**MKBHD**: 好的。
<details>
<summary>Original English</summary>

**MKBHD**: - Okay.

</details>

**主持人**: 我们只是，
我们又要做的就是。
把你的手机锁好。
手机-
<details>
<summary>Original English</summary>

**Host**: - We're just,
all we gotta do again.
Put your phone locked.
Phone-

</details>

**MKBHD**: 在这个设备上。
<details>
<summary>Original English</summary>

**MKBHD**: - On this device.

</details>

**主持人**: 锁在那台设备上。
<details>
<summary>Original English</summary>

**Host**: - Locked on that device.

</details>

**Henry**: [Henry] 是的，没错。
<details>
<summary>Original English</summary>

**Henry**: - [Henry] Yes, exactly.

</details>

**主持人**: 好的，我们
要再次启动脚本了。
好的。
(悬疑音乐)
(手机发出提示音)
<details>
<summary>Original English</summary>

**Host**: - And okay, we're gonna
start the script again.
Okay.
(suspenseful music)
(phone chimes)

</details>

**MKBHD**: [Marques] 呃呃。
(硬币叮当声)
呃呃。不行。
<details>
<summary>Original English</summary>

**MKBHD**: - [Marques] Uh-uh.
(coins clinking)
Uh-uh. No.

</details>

**主持人**: 不行？(笑)
<details>
<summary>Original English</summary>

**Host**: - No? (laughs)

</details>

**MKBHD**: 它是绿色的。已批准。
<details>
<summary>Original English</summary>

**MKBHD**: - It's just green. Approved.

</details>

**主持人**: 打印出来。打印出来。
(打印收据)
这太疯狂了。
<details>
<summary>Original English</summary>

**Host**: - Print that out. Print that.
(receipt sprinting)
That is crazy.

</details>

**MKBHD**: 天哪。所以，所以，是的，
我需要把它拿回来。
<details>
<summary>Original English</summary>

**MKBHD**: - Oh my God. So, so, yeah,
I'm gonna need that back.

</details>

**主持人**: 是的。(笑)
<details>
<summary>Original English</summary>

**Host**: - Yeah. (laughs)

</details>

**MKBHD**: 肯定，
我需要把它拿回来。
但是，它刚刚...
是的，哇。它成功了。
<details>
<summary>Original English</summary>

**MKBHD**: - For sure,
I'm gonna need that back.
But also, did that just?
Yeah, wow. It worked.

</details>

**主持人**: 10,000 美元。
<details>
<summary>Original English</summary>

**Host**: - $10,000.

</details>

**MKBHD**: 好的。我信你。
我绝对相信你。
我们怎么拿回来？
我们来个 Venmo 或 PayPal？
我们怎么才能？
<details>
<summary>Original English</summary>

**MKBHD**: - All right. I believe you.
I definitely believe you.
How do we get this back?
We do like a little Venmo or like PayPal?
How do we even?

</details>

**主持人**: 你知道，
我们真的要还回去吗？
<details>
<summary>Original English</summary>

**Host**: - You know,
do we give it back though?

</details>

**MKBHD**: 撤销交易。
我甚至不知道。我应该打电话给我的公司吗？
<details>
<summary>Original English</summary>

**MKBHD**: - Reverse the transaction.
I don't even know. Do I call my company?

</details>

**MKBHD**: 是的，太疯狂了。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah, that's crazy.

</details>

**主持人**: 是的，没错。
你可以留着这个，如果你想-
<details>
<summary>Original English</summary>

**Host**: - Yeah, exactly.
You can keep this if you wanna-

</details>

**MKBHD**: 是的。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 把它装裱起来。
<details>
<summary>Original English</summary>

**Host**: - Get it framed.

</details>

**MKBHD**: 是的。损坏收据。
我从不解锁我的手机。
我从不输入密码。
我从未做过我通常会做的事
来验证我手机上的交易。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah. A receipt of the damage.
I never unlock my phone.
I never put in a password.
I never did what I would normally do
to verify a transaction on my phone.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: - Yes.

</details>

**MKBHD**: 它只是碰巧放在上面。
<details>
<summary>Original English</summary>

**MKBHD**: - It just happened
to be on top of that.

</details>

### 攻击原理剖析：三层谎言

**主持人**: 那么，我们是怎么做到的？
嗯，我们与两位网络安全专家合作，
教授 Ioana Boureanu 和 Tom Chothia。
我们去萨里大学拜访了他们，
在那里他们向我们展示了一种他们开发的独特黑客技术，
 可以绕过手机的锁屏，
然后从其移动钱包中提取资金。
<details>
<summary>Original English</summary>

**Host**: - So, how did we do it?
Well, we teamed up with
two cybersecurity experts,
Professors Ioana Boureanu and Tom Chothia.
And we went to visit them
at the University of Surrey,
where they ran us through a
unique hack that they developed
to bypass the phone's lock
screen and then to drain funds
from inside its mobile wallet.

</details>

**MKBHD**: 在不解锁我的手机的情况下
这是真正的魔法部分。
这太疯狂了。
<details>
<summary>Original English</summary>

**MKBHD**: - Without unlocking my phone
is the real magic part.
That's crazy.

</details>

**主持人**: 而且最疯狂的是，这个黑客技术
早在 2021 年就公之于众了。
所以，人们知道在五年以来
可以用这种方式从锁定的手机上取钱。
<details>
<summary>Original English</summary>

**Host**: - And the craziest thing
of all is that this hack
was made public back in 2021.
So, people have known that it's possible
to take money from locked phones
in this way for five years.

</details>

**主持人**: 那么，这种交易金额是多少？
<details>
<summary>Original English</summary>

**Host**: - So, what kind of amounts does this?

</details>

**MKBHD**: 唯一的限制是
银行账户里有多少钱。
(悬疑音乐)
<details>
<summary>Original English</summary>

**MKBHD**: - The only limit is how much someone has
in their bank account.
(suspenseful music)

</details>

**主持人**: 然而这个漏洞
仍然没有被修复。
那么，它是如何工作的呢？
嗯，每当你使用 Tap to
Pay 时，你的手机和读卡器
会交换有关交易的信息。
但它们是通过空气
通过共享的磁场发送这些信息，
所以我们可以拦截通信并修改它。
<details>
<summary>Original English</summary>

**Host**: - Yet the loophole
still hasn't been fixed.
So, how does it work?
Well, whenever you use Tap to
Pay, your phone and the reader
exchange information
about the transaction.
But they send this
information through the air
by a shared magnetic field,
so we can intercept the
communication and alter it.

</details>

**主持人**: 我们只需要
插入我们自己的设备
在手机和读卡器之间。
<details>
<summary>Original English</summary>

**Host**: - All we need to do is to
insert our own devices
in between the phone and the reader.

</details>

**主持人**: 首先，我们将 Marques 的手机
放在这个上面。
这是一个名为 Proxmark 的 NFC 设备。
对 Marques 的手机来说，
Proxmark 看起来像
一个普通的读卡器。
<details>
<summary>Original English</summary>

**Host**: - First, we tap Marques's
phone against this.
It's an NFC device called the Proxmark.
To Marques's phone,
the proxmark looks like
a typical card reader.

</details>

**主持人**: 所以，它愉快地发送了
它的交易数据。
那个 Proxmark 然后将数据
直接发送到我们的笔记本电脑，
我们在那里运行一个 Python
脚本来修改它。
<details>
<summary>Original English</summary>

**Host**: - So, it happily sends over
its transaction data.
That proxmark then sends that
data straight to our laptop,
where we run a Python
script to modify it.

</details>

**主持人**: 接下来，笔记本电脑将数据
发送到我们的备用手机，
我把它放在实际的读卡器上。
对读卡器来说，我的手机
看起来就像 Marques 的一样。
<details>
<summary>Original English</summary>

**Host**: - Next, the laptop sends the
data to our burner phone,
which I tap on the actual card reader.
To the reader, my phone
looks just like Marques's.

</details>

**主持人**: 所以，Marques 的手机
和读卡器
都以为它们在直接通信，
但实际上它们的所有通信
都通过我们的设备系列进行。
这是一个经典的
中间人攻击。
<details>
<summary>Original English</summary>

**Host**: - So, both Marques's phone
and the card reader
think they're talking
directly to each other,
when in fact all their communication
goes through our series of devices.
This is a classic
man-in-the-middle attack.

</details>

**主持人**: 现在，进入中间
来拦截数据
实际上是很容易的部分。
难的部分是你需要对数据做什么
来欺骗手机和读卡器
授权交易。
<details>
<summary>Original English</summary>

**Host**: - Now, getting in the middle
to intercept the data
is actually the easy part.
The hard part is what you
need to do to that data
to trick the phone and the reader
into authorizing the transaction.

</details>

**主持人**: 看看，要用这个攻击
来真正盗取钱财，
你必须通过两个系统的三层防御。
<details>
<summary>Original English</summary>

**Host**: - See, to actually steal
money using this attack,
you have to get past three layers
of defense on both systems.

</details>

**主持人**: 要做到这一点，我们
必须说三句谎言。
两句对手机，一句对读卡器。
<details>
<summary>Original English</summary>

**Host**: - And to do that, we have
to tell three lies.
Two to the phone, and one to the reader.

</details>

**主持人**: 所以，第一层
防御是最简单的。
手机是锁着的。
在普通的交易中，
你需要解锁手机才能支付。
但这并非普通交易。
<details>
<summary>Original English</summary>

**Host**: - So, the first layer of
defense is the simplest.
The phone is locked.
And in an ordinary transaction,
you have to unlock your phone to pay.
But this is no ordinary transaction.

</details>

**主持人**: 所以，你知道，如果你
去地铁，
Apple 创建了一个功能，你知道，
当你走过去的时候，
他们不希望一群人排队
然后不得不解锁他们的面部。
而且你知道，他们可能穿着外套
和眼镜之类的。
<details>
<summary>Original English</summary>

**Host**: - So, you know, if you
ever go to the subway,
there's a feature that Apple's
created where you know,
when you walk through,
they don't want a bunch
of people lining up
and having to unlock their face.
And you know, maybe they're wearing a coat
and glasses and stuff.

</details>

**MKBHD**: 哦。快捷交通模式。
<details>
<summary>Original English</summary>

**MKBHD**: - Oh. Express Transit Mode.

</details>

**主持人**: Apple 在 2019 年推出了快捷交通模式
以允许你进行交通交易
而无需解锁手机。
它的工作方式是
支付终端
在地铁或巴士上会广播一条消息
表明它们是交通终端。
然后，当你轻触手机支付时，
它会查找移动钱包的
交通卡槽中有什么卡，然后
在无需解锁的情况下进行支付。
这非常方便，
但我们也可以滥用它。
<details>
<summary>Original English</summary>

**Host**: - Apple introduced express
transit mode in 2019
to let you make transit transactions
without having to unlock your phone.
The way this works is
that the payment terminals
on the subway or on the
bus broadcast a message
that identifies them
as a transit terminal.
Then, when you tap your phone to pay,
it looks for whatever card
is in the transit slot
of its mobile wallet and it
pays without needing to unlock.
This is super convenient,
but we can also abuse it.

</details>

**主持人**: 我们是通过去伦敦地铁
带着我们的笔记本电脑和设备
来弄清楚这个是如何工作的，
然后实际扫描信号
看看门在对手机说什么。
我们就是这样发现了
门发送的这个代码
解锁了手机。
<details>
<summary>Original English</summary>

**Host**: - We found out how this worked
by going to the London Underground
with our laptops and our equipment,
and actually scanning the signals
and seeing what the gate
was saying to the phone.
And that's how we discovered
this code the gate send
which unlocked the phone.

</details>

**主持人**: 我们用 Proxmark 来
广播相同的代码，
这会欺骗 Marques 的手机，让它以为
它是一个交通读卡器。
所以，当我们用 Marques 的手机
轻触 Proxmark 时，
它现在正期待接收另一条消息
包含交通交易的详情。
<details>
<summary>Original English</summary>

**Host**: - We used the proxmark to
broadcast that same code,
which fools Marques's phone into thinking
that it's a transit reader.
So, when we tap Marques's
phone against the proxmark,
it's now expecting to
receive another message
with the details about
the transit transaction.

</details>

**主持人**: 这是这条消息通常的样子
以二进制代码表示。
这些位中的每一个都携带
有关交易的重要信息。
<details>
<summary>Original English</summary>

**Host**: - Here's what that message
would typically look like
in binary code.
Each of these bits carries
important information
about the transaction.

</details>

**主持人**: 现在，这条消息中
对我们重要的部分是这个位。
真实的交通交易
这里会有一个 1。
这告诉手机读卡器可能离线。
就像在地铁地下。
在这种情况下，手机需要发送
额外的认证层。
<details>
<summary>Original English</summary>

**Host**: - Now, the important part of this
message for us is this bit.
An authentic transit transaction
would have a 1 right here.
This tells the phone that
the reader may be offline.
Like if it's underground on the subway.
In which case the phone would need to send
an extra layer of authentication.

</details>

**主持人**: 所以，当 Marques 的手机
收到来自它认为是交通读卡器的交易请求时，
它会期望该值设置为 1。
但实际上，
发送请求的设备
是我们的零售读卡器，而且
这个读卡器是在线的，
这意味着该位
当前设置为零。
因此，为了欺骗手机
接受交易，
我们拦截来自读卡器的消息，
通过我们的电脑处理，
然后我们将 0 变为 1。
<details>
<summary>Original English</summary>

**Host**: - So, when Marques's phone
receives the transaction request
from what it thinks is a transit reader,
it's gonna be expecting
that value to be set to 1.
But in reality, the
device sending the request
is our retail reader, and
this reader is online,
which means that that bit
is currently set to zero.
Therefore, to trick the phone
into accepting the transaction,
we intercept the message from the reader,
pass it through our computer,
and we change that 0 to a 1.

</details>

**主持人**: 所以当消息
到达 Marques 的手机时，
它看起来像是一笔交通交易。
由于通信通过我们的计算机进行，
我们正在说服手机
它实际上是在与交通终端通信。
但现在还有第二层防御
我们需要突破。
有了这第一句谎言，
我们绕过了解锁手机的需要。
<details>
<summary>Original English</summary>

**Host**: - So by the time the message
gets to Marques's phone,
it looks like a transit transaction.
As this communicates through our computer,
we're convincing the phone
that it is in fact talking
to a transit terminal.
But now there's a second line
of defense we need to break.
With this first lie,
we bypassed the need to unlock the phone.

</details>

**主持人**: 我们可以现在欺骗它
进行少量金额的支付。
就像你在地铁上期望的那样。
但如果我们突然要求手机
支付 10,000 美元，
嗯，它的警惕性会大大提高。
毕竟，一个交通读卡器
要求这么高的金额是很不寻常的。
<details>
<summary>Original English</summary>

**Host**: - And we can now trick it
into making small
payments of a few dollars.
Kind you'd expect on the subway.
But if we suddenly went and
asked the phone for $10,000,
well, its guard would go way back up.
After all, it's pretty
unusual for a transit reader
to ask for such a large amount of money.

</details>

**主持人**: 所以，这激活了
第二层防御。
客户验证。
对于这种非接触式支付，
有两种交易类别。
我们有高价值和低价值。
任何被归类为高价值的交易
都需要客户进行额外验证。
<details>
<summary>Original English</summary>

**Host**: - So, this activates a
second layer of defense.
Customer verification.
On contactless payments like this,
there are two categories of transaction.
We got high value and low value.
Any transaction that's
classified as high value
requires additional
verification from the customer.

</details>

**主持人**: 例如，在英国，
大多数银行都需要 PIN 码
或指纹或面部识别
对于任何超过 100 英镑的交易。
<details>
<summary>Original English</summary>

**Host**: - For example, in the UK,
most banks require a pin
or a fingerprint or facial recognition
for any transaction over 100 pounds.

</details>

**主持人**: 所以，为了让我们
10,000 美元的支付通过
而无需客户验证，
我们需要欺骗手机，让它认为
10,000 美元实际上
是一笔低价值交易。
这实际上非常简单。
这是因为为了确定
交易是高价值还是低价值，
Marques 的手机实际上不看
10,000 美元的数值。
它只看另一个
交易数据中的单个信息位。
这里的 1 表示高
价值，0 表示低。
<details>
<summary>Original English</summary>

**Host**: - So, for us to get this
$10,000 payment through
without customer verification,
we need to trick the phone into thinking
that $10,000 is in fact
a low value transaction.
And that's actually surprisingly simple.
That's because to determine
whether the transaction is high value,
Marques's phone doesn't actually look
at the numerical value of $10,000.
It just looks at another
single bit of information
in the transaction data.
A 1 here means high
value and 0 means low.

</details>

**主持人**: 原因在于高低价值的界限
因国家而异。
而且，当然，
不同的国家有
不同的货币。
所以，一个简单的标签允许灵活性
来处理这些差异。
它允许在不发行新卡的情况下更改限额。
<details>
<summary>Original English</summary>

**Host**: - The reason for this is that the boundary
between high and low value
varies from country to country.
And of course,
different countries operate
in different currencies.
So, a simple label allows the flexibility
to deal with these variations.
And it allows the limits to be changed
without the banks needing
to issue new cards.

</details>

**主持人**: 所以，我们所要做的
就是拦截读卡器的消息，
将其位翻转为零，
然后手机就会相信
这笔交易是低价值的
即使它是 10,000 美元。
然后，当手机收到我们
10,000 美元交易的请求时，
它不会要求客户验证。
它只会继续
授权交易。
<details>
<summary>Original English</summary>

**Host**: - So, all we need to do
is intercept the message from the reader,
flip that bit to a zero,
and then the phone will believe
that this transaction is low value
even though it's for $10,000.
Then, when the phone receives our request
for a $10,000 transaction,
it doesn't ask for customer verification.
It just goes ahead and
authorizes the transaction.

</details>

**主持人**: 现在，你可能会问，
为什么这些数据如此容易被篡改？
我们稍后会讲到。
但我们还有最后一个
安全检查要克服。
<details>
<summary>Original English</summary>

**Host**: - Now, you might be asking,
why is this data so easy to tamper with?
And we'll get to that in just a minute.
But we have one final
security check to overcome.

</details>

**主持人**: 看看，用这两句谎言，
我们绕过了解锁手机
然后欺骗它进行了一笔高价值交易
而无需验证。
所以，手机完全被说服了
它准备好付款了。
但我们仍然需要说服读卡器
交易是有效的。
这正是我们的第三句谎言的由来。
<details>
<summary>Original English</summary>

**Host**: - See, with these first two lies,
we bypassed unlocking the phone
and then tricked it into
making a high value transaction
without asking for verification.
So, the phone is fully convinced
and it's ready to make the payment.
But we still need to convince the reader
that the transaction's valid.
And this is where our third lie comes in.

</details>

**主持人**: 当 Marques 的手机回复时，
它说它已批准
10,000 美元的交易。
但它也说它没有要求
客户验证。
没有 PIN 码，没有指纹，
没有面部识别。
但是，如果读卡器看到这个，
它会拒绝交易
因为它知道它最初要求的
10,000 美元支付是高价值的。
因此，它应该要求
客户验证。
<details>
<summary>Original English</summary>

**Host**: - When Marques's phone replies,
it says it's approved
the $10,000 transaction.
But it also says that it hasn't asked
for customer verification.
No pin, no fingerprint,
no facial recognition.
But if the reader sees this,
it'll reject the transaction
because it knows that the $10,000 payment
it originally asked for is high value.
It should therefore require
customer verification.

</details>

**主持人**: 所以，现在我们需要欺骗读卡器
以为客户
已经验证了付款。
所以，我们拦截了
Marques 手机的回复
并寻找那个说
客户验证未完成的信息位。
然后我们将其更改为说
付款已验证
通过将这个 0 变为 1。
<details>
<summary>Original English</summary>

**Host**: - So, now we need to trick the reader
into thinking that the customer
has verified the payment.
So, we intercept the
response from Marques's phone
and look for the bit of information
that says customer
verification hasn't been done.
Then we change it to say that
the payment has been verified
by flipping this 0 to a 1.

</details>

**主持人**: 现在，读卡器很满意。
它将信息转发给银行，
银行授权了付款。
毕竟，它看到了一笔交易
已被客户在其设备上验证。
(欢快的音乐)
(通知蜂鸣声)
绿色已批准。
(硬币叮当声)
<details>
<summary>Original English</summary>

**Host**: - Now, the reader's happy.
It forwards the information onto the bank,
and the bank authorizes the payment.
After all, it sees a
transaction that's been verified
by the customer on their device.
(upbeat lively music)
(notification beeps)
Green approved.
(coins clinking)

</details>

**MKBHD**: 这太疯狂了。
<details>
<summary>Original English</summary>

**MKBHD**: - That is crazy.

</details>

**主持人**: 设备已验证？
<details>
<summary>Original English</summary>

**Host**: - Verified on device?

</details>

**MKBHD**: 是的，已验证。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah, verified.

</details>

**主持人**: 你没有，你没有验证它。
<details>
<summary>Original English</summary>

**Host**: - You didn't, you didn't verify it.

</details>

**MKBHD**: 对。
<details>
<summary>Original English</summary>

**MKBHD**: - Right.

</details>

**主持人**: 那么，为什么所有这些信息
都没有加密呢？
那样就无法秘密篡改了。
<details>
<summary>Original English</summary>

**Host**: - So, why isn't all this
information encrypted?
That would make it impossible
to secretly tamper with.

</details>

**主持人**: 嗯，手机
和读卡器通信的方式
必须与数千种不同的设备兼容，
这不可能一次性全部更新。
<details>
<summary>Original English</summary>

**Host**: - Well, the way the phone
and reader communicate
has to be compatible with
thousands of different devices,
which would be impossible
to update all in one go.

</details>

**主持人**: 因此，我们到目前为止查看的信息
只是以明文形式发送。
<details>
<summary>Original English</summary>

**Host**: - So for that reason, the
information we've looked at so far
is just sent across unencrypted.

</details>

**主持人**: 即使如此，手机、读卡器和银行
都有检查措施来确保
这样的攻击不会发生。
<details>
<summary>Original English</summary>

**Host**: - Even still, phones, readers and banks
all have checks in place to make sure
an attack like this can't happen.

</details>

**主持人**: 通常，它不会发生。
除非你碰巧使用了
特定类型的手机
和特定类型的卡。
<details>
<summary>Original English</summary>

**Host**: - And normally, it can't.
Except if you happen to use
a specific type of phone
and a specific type of card.

</details>

**主持人**: 因为当它们
在这种特定情况下结合时，
它们会产生一个漏洞。
<details>
<summary>Original English</summary>

**Host**: - Because when you combine them
in this particular scenario,
they create a loophole.

</details>

**主持人**: 所以，我们的黑客技术依赖于特定的手机
和信用卡组合。
而且我们还使用了一种复杂的方法
由网络安全专家开发的。
但黑客或在线诈骗犯，
嗯，他们不需要那么聪明。
<details>
<summary>Original English</summary>

**Host**: - So, our hack relied on a specific phone
and credit card combination.
And we also use a sophisticated method
developed by cybersecurity experts.
But hackers or scammers online,
well, they don't need to be that smart.

</details>

**主持人**: 他们通常可以直接购买信息来定位你。
<details>
<summary>Original English</summary>

**Host**: - Often they can just buy
information to target you.

</details>

**MKBHD**: 当我开始在 Veritasium 工作时，
我去出差去
第一次见到 Derek。
然后我收到一封邮件
有人说他是 Derek
向我要我的电话号码。
这非常合理。
我正要离开机场。
<details>
<summary>Original English</summary>

**MKBHD**: - When I started working at Veritasium,
I was on a work trip to go
meet Derek for the first time.
And I got an email from
somebody was saying he was Derek
asking for my phone number.
That made a ton of sense.
I was leaving the airport.

</details>

**MKBHD**: 所以，我只是回复了
发了我的电话号码。
我立刻就想，
“等等，我得看看。”
我检查了邮件。不是 Derek。
当然，接下来的几个月
我一直接到诈骗电话。
<details>
<summary>Original English</summary>

**MKBHD**: - So, I just responded by
sending my phone number.
I immediately was like,
"Wait, let me look at that."
I checked the email. Not Derek.
Of course, for the next few months
I was just getting scam
call after scam call.

</details>

**MKBHD**: 这是他们能抓到你的一个方式。
我感觉自己像个白痴。
但不仅仅是这样的诈骗电话。
在一次重大数据泄露的新闻之后
我也曾有过那种感觉。
我一直在想，
我使用某个网站
是否导致我的个人信息
在不知情的情况下被暴露在某个地方。
<details>
<summary>Original English</summary>

**MKBHD**: - That's one way they can get
you. I felt like an idiot.
But it's not just scam calls like that.
I've also had that feeling
after news of a major data breach.
I've wondered whether
me using some website
has led to my personal information
being exposed somewhere
without me even knowing about it.

</details>

**主持人**: 但你可以保护你的个人信息
通过我们今天的赞助商 Incogni。
<details>
<summary>Original English</summary>

**Host**: - But you can protect your personal info
with today's sponsor, Incogni.

</details>

**主持人**: 看看，每当诈骗犯购买
你的电子邮件、电话号码，
甚至你的家庭住址
来自数据经纪人时，
Incogni 会自动化繁琐的请求过程
让这些数据经纪人删除你的信息。
<details>
<summary>Original English</summary>

**Host**: - See, whenever scammers purchase
your email, phone number,
and even your home
address from data brokers,
Incogni automates the
grueling process of requesting
that these data brokers
delete your information.

</details>

**MKBHD**: 好的，我从 2025 年 6 月开始使用它。
从那时起，我们已经有了 94
次不同的删除请求。
我真的很喜欢你
可以在这里追踪进度
在这个仪表板上。
<details>
<summary>Original English</summary>

**MKBHD**: - Okay, so I've had this since June 2025.
And since then, we've had 94
different removal requests.
And I really like how you
can track the progress
in this dashboard here.

</details>

**MKBHD**: 他们估计这为我节省了
70 小时 30 分钟的时间
如果我自己联系
这些人。
<details>
<summary>Original English</summary>

**MKBHD**: - They've estimated that that saved me
70 hours and 30 minutes of my own time
if I were to reach out
to these people myself.

</details>

**MKBHD**: 而且 Incogni 的新
定制删除功能
在他们的无限套餐中，
你可以指向任何可见你信息
的特定网站。
然后，我们的一位隐私代理人
将处理其余的事情。
<details>
<summary>Original English</summary>

**MKBHD**: - And with Incogni's new
custom removal feature
in their unlimited plans,
you can point to any specific site
where your information is visible.
And then, one of their privacy agents
will take care of the rest.

</details>

**MKBHD**: 所以，今天就把你的数据
从市场上移除，
前往 incogni.com/veritasium
然后使用 Veritasium 代码可享受 60% 折扣。
你可以点击下面的链接
或者扫描这个二维码
来获得 60% 的折扣
并将你的个人数据从市场上移除。
<details>
<summary>Original English</summary>

**MKBHD**: - So, to take your data
off the market today,
go to incogni.com/veritasium
and then use code Veritasium for 60% off.
You can click the link below
or you can scan this QR
code to claim that 60% off
and get your personal data off the market.

</details>

**MKBHD**: 我想感谢 Incogni
赞助这个关于从 Marques Brownlee 那里盗取金钱的视频。
现在，让我们回到那个话题。
<details>
<summary>Original English</summary>

**MKBHD**: - I wanna thank Incogni
for sponsoring this video
about taking money from Marques Brownlee.
And now, let's get back
to that thing.

</details>

### 技术细节：加密与Visa的漏洞

**主持人**: 那么，是哪种组合的卡和手机
使得这个黑客技术成为可能？
<details>
<summary>Original English</summary>

**Host**: - So, which combination of card and phone
make this hack possible?

</details>

**主持人**: 首先，手机必须是 iPhone。
正如我们之前看到的，当
iPhone 决定
是否要求客户验证时，
它不看交易的数值。
它只看读卡器提供的
高价值或低价值标签。
<details>
<summary>Original English</summary>

**Host**: - Firstly, the phone has to be an iPhone.
As we saw earlier, when
an iPhone is deciding
whether to ask for customer verification,
it doesn't look at the numerical
value of the transaction.
It only looks at the high
value or low value label
provided by the reader.

</details>

**主持人**: 但其他手机则不然。
例如，当三星手机
进入交通模式时，
它不依赖于读卡器提供的低价值标签。
它查看交易的实际数值
并且只接受 0 美元的付款。
<details>
<summary>Original English</summary>

**Host**: - But other phones don't work that way.
For example, when a Samsung
phone goes into transit mode,
it doesn't rely on this low
value label from the reader.
It looks at the actual numerical
value of the transaction
and it only accepts a payment of $0.

</details>

**主持人**: 然后它依赖于交通提供商
来计算你使用地铁的次数，
然后一天结束时给你寄账单。
所以，如果三星手机
看到交通终端
试图向你收取一次刷卡 10,000 美元，
它会立即拒绝。
<details>
<summary>Original English</summary>

**Host**: - Then it relies on the transport provider
to count up all the times
you've used the subway,
and then to send you a
bill at the end of the day.
So, if a Samsung phone
saw a transit terminal
trying to charge you
$10,000 for a single tap,
it would immediately reject it.

</details>

**主持人**: 但不仅仅是 Apple 的交通模式
让这个黑客技术成为可能。
你得有一张
特定类型的卡
在交通卡槽里。
<details>
<summary>Original English</summary>

**Host**: - But it's not just Apple's transit mode
that makes this hack possible.
You've gotta have one
specific type of card
in the transit slot.

</details>

**MKBHD**: 这是 Apple 和 Visa 的混合使用方式
真正引入的一个设计特性。
<details>
<summary>Original English</summary>

**MKBHD**: - It was truly a design
feature that was introduced
by the way you mixed Apple and Visa.

</details>

**主持人**: 而这
与 Visa 卡一起工作，
但与万事达卡则不同
的原因在于它们使用的
验证交易的不同过程。
<details>
<summary>Original English</summary>

**Host**: - And the reason that this
works with a Visa card,
but wouldn't, with say, a MasterCard
comes down to the different
processes they use
to verify transactions.

</details>

**主持人**: 那么，Visa 的验证过程
有什么特别之处
使得这个黑客技术成为可能？
<details>
<summary>Original English</summary>

**Host**: - So, what is it about
Visa's verification process
that makes this hack possible?

</details>

**主持人**: 在之前的视频中，我们看到
任何银行卡交易
都依赖于银行和银行卡之间共享的
秘密加密密钥。
<details>
<summary>Original English</summary>

**Host**: - In a previous video, we saw
that any card transaction
relies on a secret cryptographic key
shared by the card and the bank.

</details>

**主持人**: 当你将卡
或手机刷到读卡器上时，
读卡器会发送一长串交易细节。
然后银行卡使用其秘密
密钥来搅乱该消息
生成交易的唯一代码。
银行卡将此发送给读卡器，
读卡器将其连同原始交易细节
一起转发给银行。
<details>
<summary>Original English</summary>

**Host**: - When you tap the card
or phone onto a reader,
the reader sends across
a long string of transaction details.
The card then applies its secret
key to garble that message
into a unique code for the transaction.
The card sends this to the reader,
which the reader forwards onto the bank,
along with the raw transaction details.

</details>

**主持人**: 然后银行也会对其数据应用自己的秘密
密钥。
如果输出与银行卡的一致，
银行就会授权交易。
<details>
<summary>Original English</summary>

**Host**: - The bank then applies its own secret key
to the raw data as well.
And if the output matches
the one from the card,
the bank authorizes the transaction.

</details>

**主持人**: 这被称为对称加密
因为银行卡和银行
使用相同的秘密密钥。
<details>
<summary>Original English</summary>

**Host**: - This is called symmetric cryptography
since the card and the bank
use the same secret key.

</details>

**主持人**: 并且所有交易
都必需此步骤。
无论你持有 Visa、万事达卡
还是其他卡。
<details>
<summary>Original English</summary>

**Host**: - And this step is required
in all transactions.
No matter whether you
have a Visa, a MasterCard,
or something else.

</details>

**主持人**: 但实际上还有另一层安全
万事达卡在其所有交易中都会使用。
<details>
<summary>Original English</summary>

**Host**: - But there's actually
another layer of security
which MasterCard uses in
all of its transactions.

</details>

**主持人**: 但在这种特殊情况下，Visa 不使用。
这一层安全不是
在银行卡和银行之间，
而是在银行卡和读卡器之间。
正是在这一步，
万事达卡阻止了我们的攻击。
<details>
<summary>Original English</summary>

**Host**: - But in this particular case, Visa doesn't.
This layer of security is not
between the card and the bank,
but between the card and the reader.
And it's at this step where
MasterCard thwarts our attack.

</details>

**主持人**: 第二步依赖于
非对称加密。
所谓非对称加密
因为它使用两个不同的密钥。
银行卡有一个私钥，
读卡器有一个公钥。
<details>
<summary>Original English</summary>

**Host**: - The second step relies on
asymmetric cryptography.
So-called because it
uses two different keys.
A private key for the card and
a public key for the reader.

</details>

**主持人**: 它开始时，读卡器将
交易细节发送给
银行卡，就像之前一样。
然后银行卡使用其私钥
将该消息搅乱
变成另一串数字。
<details>
<summary>Original English</summary>

**Host**: - It starts with the reader sending across
the transaction details to
the card just like before.
The card then uses its private
key to garble that message
into another long string of digits.

</details>

**主持人**: 这是银行卡的数字签名
对于这次交易。
银行卡将此签名
连同公钥一起发送回读卡器，
读卡器然后用它来验证签名
是否来自该特定银行卡
用于此特定交易。
<details>
<summary>Original English</summary>

**Host**: - This is the card's digital
signature for the transaction.
The card sends this
signature back to the reader
along with the public key,
which the reader then uses
to verify that the signature
came from that specific card
for this specific transaction.

</details>

**主持人**: 为了说明它的工作原理，
我们来举一个简单的例子。
私钥和公钥都包含两个组件。
N 是一个共享数字。
在这种情况下，假设是 55。
D 是银行卡的私有
数字。假设是 7。
E 是公有数字。假设是 3。
<details>
<summary>Original English</summary>

**Host**: - To illustrate how this works,
let's consider a simple example.
The private key and public
key both have two components.
N is a shared number.
In this case, let's say 55.
D is the card's private
number. Let's say 7.
And E is the public number. Let's say 3.

</details>

**主持人**: 现在，当读卡器发送
原始交易数据时，
它将其表示为一个长数字。
但为了简化，我们将
使用一个小的数字。
比如 2。
<details>
<summary>Original English</summary>

**Host**: - Now, when the reader sends
across the raw transaction data,
it represents it as one long number.
But for simplicity, we'll
use a much smaller one.
Let's say 2.

</details>

**主持人**: 为了签名交易，
银行卡或手机
将交易号（本例为 2）
提高到其私有
数字的幂，所以我们得到 128。
然后除以
共享数字，128 除以 55，
余数为 18。
这就是银行卡签名，18，
它发送给读卡器。
<details>
<summary>Original English</summary>

**Host**: - To sign for the transaction,
the card or the phone
raises the transaction
number, in this case 2,
to the power of its private
number, so we get 128.
And then divides this by the
shared number, 128 over 55,
which leaves a remainder of 18.
And this is the card signature, 18,
which it sends on to the reader.

</details>

**主持人**: 现在，读卡器需要知道
交易是否有效。
所以，它获取银行卡签名
并将其提高到
公有数字的幂。
然后，它取除以共享数字 55
的余数。
<details>
<summary>Original English</summary>

**Host**: - Now, the reader needs to know
whether the transaction is valid.
So, it takes the card signature
and raises it to the power
of the public number.
Then, it takes the remainder
when you divide by the shared number 55.

</details>

**主持人**: 你得到 2。
这与读卡器发送给银行卡
的原始交易数据相匹配。
<details>
<summary>Original English</summary>

**Host**: - And you get 2.
This matches the original transaction data
the reader sent to the card.

</details>

**主持人**: 之所以有效，是因为
私有和公有数字
经过特殊选择，
以便与共享数字结合时，
公有密钥有效地
逆转了私有密钥的操作。
<details>
<summary>Original English</summary>

**Host**: - The reason this works is that
the private and public numbers
are specifically chosen
so that when combined
with the shared number,
the public key effectively
reverses the operation
of the private key.

</details>

**主持人**: 这允许读卡器验证
银行卡签名是否有效
而无需看到其私有号码。
这基于一种称为 RSA 的
加密类型。
<details>
<summary>Original English</summary>

**Host**: - And this allows the reader to verify
that the card signature is valid
without ever having
seen its private number.
This is based on a type of
cryptography called RSA.

</details>

**主持人**: 实际上，涉及的数字要大得多。
但这使其非常安全，
因为这使得逆向工程
银行卡的私有密钥
几乎不可能。
<details>
<summary>Original English</summary>

**Host**: - In reality, the numbers
involved are much larger.
But that makes it incredibly secure
because that makes it virtually impossible
to reverse engineer
the card's private key.

</details>

**主持人**: 而且它也意味着
即使交易数据中
有一个数字发生变化，
当读卡器检查
手机签名时也会产生不同的结果，
在这种情况下，读卡器
将不会批准交易。
<details>
<summary>Original English</summary>

**Host**: - And it also means that
even a one digit change
in the transaction data will
produce a different result
when the reader checks
the phone's signature,
in which case the reader
won't approve the transaction.

</details>

**主持人**: 这是一个问题，因为
我们修改了数据。
读卡器期望的是
高价值零售交易的签名。
但我们拦截了通信。
所以手机签名
实际上是低价值的
交通交易。
<details>
<summary>Original English</summary>

**Host**: - This is a problem because
we've modified the data.
The reader's expecting a signature
for a high value retail transaction.
But we intercepted the communication.
So the phone signature
is actually for low value
transit transaction.

</details>

**主持人**: 这将无法通过
非对称签名检查。
<details>
<summary>Original English</summary>

**Host**: - This wouldn't pass the
asymmetric signature check.

</details>

**主持人**: 但是，万事达卡总是要求
这种非对称验证，
它会发现我们的黑客技术，而 Visa 不。
它们只在某些情况下要求
这个签名。
比如，当读卡器离线时。
<details>
<summary>Original English</summary>

**Host**: - But while MasterCard always requires
this asymmetric verification,
which would spot our hack, Visa doesn't.
They only require this
signature in certain situations.
Like, when the reader's offline.

</details>

**主持人**: 例如，当你
在没有信号的地下时，
读卡器无法与银行通信
进行第一层
对称加密。
至少直到它重新上线。
<details>
<summary>Original English</summary>

**Host**: - For example, when you're
underground with no signal,
there's no way for the reader
to communicate with the bank
for that first layer of
symmetric cryptography.
At least not until it comes back online.

</details>

**主持人**: 所以，在我们的攻击中，
我们确保读卡器
全程在线。
这样，它就不会费力去使用
非对称安全层，
其中包含会揭穿我们谎言的签名。
<details>
<summary>Original English</summary>

**Host**: - So, during our attack,
we make sure the reader
is online the whole time.
That way, it doesn't bother using
the asymmetric layer of security,
which contains the signature
that would unravel our lies.

</details>

**主持人**: 但有趣的是
我们欺骗了手机
以为它正在与交通读卡器通信。
而交通交易
正是 Visa 要求
非对称签名的一些情况之一，
因为读卡器可能在地铁地下，
因此离线。
<details>
<summary>Original English</summary>

**Host**: - But the funny thing is
we've tricked the phone
into thinking it's interacting
with the transit reader.
And transit transactions
are one of those times
where Visa does require
the asymmetric signature,
since the reader could be
underground on the subway,
and therefore offline.

</details>

**主持人**: 所以，手机确实发送了
它的签名给读卡器，
但读卡器并没有检查它。
因为实际上，读卡器是在线的。
<details>
<summary>Original English</summary>

**Host**: - So, the phone actually does send across
its signature to the reader,
but the reader doesn't check it.
Because in reality, the reader's online.

</details>

**主持人**: 所以，它只是依赖
银行的第一层安全，
即使它检查了手机签名，
它也拥有停止黑客所需的一切证据。
(屏幕嗖嗖声)
<details>
<summary>Original English</summary>

**Host**: - So, instead it just relies
on that first layer of
security with the bank,
even though if it did
check the phone signature,
it would've all the evidence
it needed to stop the hack.
(screen whooshing)

</details>

**主持人**: 所以，你看，你去吧。
<details>
<summary>Original English</summary>

**Host**: - So yeah, you go.

</details>

**MKBHD**: 觉得它如此复杂
是有道理的
因为这本不该如此容易，
但这仍然太容易了。
<details>
<summary>Original English</summary>

**MKBHD**: - Makes sense
that it's that sophisticated
'cause it shouldn't be that easy,
but that still seemed way too easy.

</details>

**主持人**: 而 Marques 不是唯一的受害者。
<details>
<summary>Original English</summary>

**Host**: - And Marques was not the only victim.

</details>

**主持人**: 我认为公平起见，
我先对自己进行尝试。
(手机哔哔声)
<details>
<summary>Original English</summary>

**Host**: - I thought it was only fair
that I first try it out on myself.
(phone beeping)

</details>

**主持人**: 批准了。
<details>
<summary>Original English</summary>

**Host**: - Approved it.

</details>

**MKBHD**: 哇呼呼！
<details>
<summary>Original English</summary>

**MKBHD**: - Woohoohoo!

</details>

**主持人**: 是的，给你。这是来自
Tom 和我的英国纪念品。
<details>
<summary>Original English</summary>

**Host**: - Yeah, here. You souvenir
from the UK from Tom and me.

</details>

**MKBHD**: 哦，多漂亮的收据
这次盗窃的。(笑)
<details>
<summary>Original English</summary>

**MKBHD**: - Oh, what a lovely receipt
for this theft. (chuckles)

</details>

**MKBHD**: 然后我又有了一个受害者
有一个更大的预算。
我们的频道基本上有一个 CFO，
他住在附近。
<details>
<summary>Original English</summary>

**MKBHD**: - And then I got another victim
with a bit of a bigger budget.
Our channel has a CFO basically,
who lives very nearby.

</details>

**主持人**: 我们正在做的，我们正在设置为
就是你的交通卡。
<details>
<summary>Original English</summary>

**Host**: - What we're doing is we're setting it
to be your transit card.

</details>

**CFO**: 好的。
<details>
<summary>Original English</summary>

**CFO**: - Okay.

</details>

**主持人**: 所以这意味着
如果你在伦敦
你必须用地铁-
<details>
<summary>Original English</summary>

**Host**: - So that means
that if you're in, London 
you have to use the tube-

</details>

**CFO**: 是的。
<details>
<summary>Original English</summary>

**CFO**: - Yeah.

</details>

**主持人**: 它会从这张卡上扣钱。
<details>
<summary>Original English</summary>

**Host**: - It'll take money
from this card.

</details>

**CFO**: 刚才发生了什么。
<details>
<summary>Original English</summary>

**CFO**: - Something just happened.

</details>

**主持人**: 是的。
(众人笑)
<details>
<summary>Original English</summary>

**Host**: - Yeah.
(everyone laughs)

</details>

**CFO**: 你感觉怎么样？
<details>
<summary>Original English</summary>

**CFO**: - How you feel about that?

</details>

**CFO**: 哦，我的天哪。
哦，我的-
<details>
<summary>Original English</summary>

**CFO**: - Oh my goodness me.
Oh my-

</details>

**Henry**: [Henry] 给你。
<details>
<summary>Original English</summary>

**Henry**: - [Henry] There you go.

</details>

**CFO**: 我们只是要去喝一杯。
那就是，你知道，
那是我们约好的。
<details>
<summary>Original English</summary>

**CFO**: - We were just gonna meet for a drink.
That's what, you know,
that was the agreement.

</details>

### 影响与责任：谁该负责？

**主持人**: 在现实世界中，比如说你的手机
放在口袋里。
<details>
<summary>Original English</summary>

**Host**: - In the real world, say you
had your phone in your pocket.

</details>

**CFO**: 是的。
<details>
<summary>Original English</summary>

**CFO**: - Yeah.

</details>

**主持人**: 我会从你身边走过-
<details>
<summary>Original English</summary>

**Host**: - I would walk by you-

</details>

**CFO**: 是的。
<details>
<summary>Original English</summary>

**CFO**: - Yeah.

</details>

**主持人**: 这样做。
<details>
<summary>Original English</summary>

**Host**: - Doing this.

</details>

**主持人**: 然后 Tom 会在商店里
付款。
<details>
<summary>Original English</summary>

**Host**: - And Tom would have this
in the shop and pay.

</details>

**CFO**: 这成为犯罪的最简单方式
会是一部被盗的 iPhone。
<details>
<summary>Original English</summary>

**CFO**: - The easiest way for this
to actually be a crime
would be a stolen iPhone.

</details>

**Henry**: [Henry] 当然。
<details>
<summary>Original English</summary>

**Henry**: - [Henry] Sure.

</details>

**CFO**: 然后有人去
花成千上万英镑。
<details>
<summary>Original English</summary>

**CFO**: - And then someone goes and
spends thousands of pounds.

</details>

**主持人**: 所以你知道，你可以买辆车
用这个。
<details>
<summary>Original English</summary>

**Host**: - So you know, you
could buy a car with us.

</details>

**CFO**: 天哪。是的，是的。
理论上。天哪。
<details>
<summary>Original English</summary>

**CFO**: - Jesus. Yeah, yeah.
Theoretically. Geez.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: - Yeah.

</details>

**CFO**: 哇。
<details>
<summary>Original English</summary>

**CFO**: - Wow.

</details>

**MKBHD**: 我觉得从你的角度来看，
你公布了所有这些信息
并告诉我们。
我们正在详细地进行讲解。
我们如何阻止人们使用这个？
或者我们能阻止人们吗？
<details>
<summary>Original English</summary>

**MKBHD**: - I guess from your perspective,
you've revealed all this
information publicly
and you're telling us.
We're walking through it in great detail.
How do we stop people from using this for-
Or can we stop people?

</details>

**MKBHD**: 比如，谁的责任
来阻止这个？
<details>
<summary>Original English</summary>

**MKBHD**: - Like, whose responsibility
is it to stop this?

</details>

**主持人**: 哦，谁的责任
这是一个有趣的问题。
<details>
<summary>Original English</summary>

**Host**: - Oh, whose responsibility is
it is an interesting question.

</details>

**MKBHD**: 是啊。
<details>
<summary>Original English</summary>

**MKBHD**: - Yeah.

</details>

**主持人**: 但你可以通过
关闭交通模式来阻止它。
<details>
<summary>Original English</summary>

**Host**: - But you can stop it
by turning transit mode off.

</details>

**MKBHD**: 或者不关闭它，
但不要在 Apple 上
有 Visa 卡处于交通模式。
<details>
<summary>Original English</summary>

**MKBHD**: - Or not turn it off,
but not have a Visa card
in transit mode on an Apple.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: - Yes.

</details>

**主持人**: 而且你确实需要小心
因为一旦你
在你的 Apple 钱包里放了合适的卡，
快捷交通模式
就是默认开启的。
<details>
<summary>Original English</summary>

**Host**: - And you do need to be careful
because as soon as you
have a suitable card
in your Apple wallet,
Express Transit Mode is
turned on by default.

</details>

**主持人**: 这个黑客技术最早是在 2021 年
公布的，
在教授们私下通知
Apple 和 Visa 之后。
<details>
<summary>Original English</summary>

**Host**: - This hack was first made
public way back in 2021
after the professors had informed
Apple and Visa privately.

</details>

**主持人**: 要弄清楚为什么它仍然可能，
我们联系了 Apple，
他们没有同意采访。
但他们是这么说的。
<details>
<summary>Original English</summary>

**Host**: - And to get to the bottom
of why it's still possible,
we reached out to Apple,
and they didn't agree to an interview.
But here's what they said.

</details>

**主持人**: “这是 Visa 系统的问题，
但 Visa 不认为
这种欺诈
很可能在现实世界中发生。
Visa 已明确表示，其持卡人
受到 Visa 的
零责任政策的保护。”
<details>
<summary>Original English</summary>

**Host**: - "This is a concern with the Visa system,
but Visa does not believe
this kind of fraud
is likely to take place in the real world.
Visa has made it clear
that their cardholders
are protected by Visa's
zero liability policy."

</details>

**主持人**: 这与他们
在黑客技术首次
在 2021 年公布时的立场完全相同。
<details>
<summary>Original English</summary>

**Host**: - This is exactly the same as their position
when the hack was first
made public back in 2021.

</details>

**主持人**: 所以，看来 Apple
基本上是在说，
“嗯，这是 Visa 的问题。”
<details>
<summary>Original English</summary>

**Host**: - So, it seems like Apple
are basically saying,
"Well, this is a Visa problem."

</details>

**主持人**: 所以，我们去问了
Visa 他们怎么看。
<details>
<summary>Original English</summary>

**Host**: - So, we went and asked
Visa what they thought.

</details>

**Visa 代表**: 我认为这个特定的漏洞
很可能存在于受控环境中。
在规模化的真实环境中
不太可能发生。
<details>
<summary>Original English</summary>

**Visa Representative**: - I think this specific vulnerability
is likely within a controlled setting.
Very unlikely from a
scaled real world setting.

</details>

**Visa 代表**: 然后，从消费者的角度来看，
在这次事件成功的情况下，
他们有能力
对该交易提出异议
并获得退款。
<details>
<summary>Original English</summary>

**Visa Representative**: - And then, kind of the last point
is from a consumer perspective,
is that in the cases
where this is successful,
they have the ability to
dispute this transaction
and get their refunds returned to them.

</details>

**MKBHD**: 我觉得这很公平。
你的意思是它并不完全可扩展，
然后即使它发生了，
我们会给你钱。
就像，这是一个很好的，
一个很好的立场。
<details>
<summary>Original English</summary>

**MKBHD**: - I think that's fair.
You're saying it's not entirely scalable,
and then even if it does happen,
we'll give you your money back.
Like, that's a great,
that's a great stance.

</details>

**MKBHD**: 我仍然认为，很多人，
我认为我们的观众
会非常想听到
你们实际上正在进行技术更改
以阻止这种情况再次发生。
<details>
<summary>Original English</summary>

**MKBHD**: - I still think though, a lot of people,
and I think our audience
would really wanna hear
that you're actually making
the technical changes
to stop this from ever happening again.

</details>

**Visa 代表**: 因为当你从规模的角度来看
以及我们网络级别的防御
是否足以确保
这种类型的
漏洞被隔离，
我们认为它是有效的。
<details>
<summary>Original English</summary>

**Visa Representative**: - 'Cause when you think about
it from a scale perspective
and whether the network level defenses
that we have are effective in making sure
that this type of
vulnerability is isolated,
we believe it is effective.

</details>

**Visa 代表**: 因为如果不是，你
就会听到更多数据
关于这是一个问题，而它根本不是。
<details>
<summary>Original English</summary>

**Visa Representative**: - Because if it wasn't, you
would hear a lot more data
about how this is an
issue, and it simply isn't.

</details>

**Visa 代表**: 我要说的是，你永远不可能
完全根除
任何特定类型的欺诈
因为它会存在，对吧？
<details>
<summary>Original English</summary>

**Visa Representative**: - The point that I'm making is
that you're never gonna be able
to completely eradicate
any specific type of fraud
'cause it's going to exist, right?

</details>

**MKBHD**: 是的。
<details>
<summary>Original English</summary>

**MKBHD**: - Yes.

</details>

**Visa 代表**: 我说的是，我们有正确的
检测措施来确保
这种类型的欺诈不是普遍存在的。
<details>
<summary>Original English</summary>

**Visa Representative**: - What I'm saying
is that we have the right
detections in place to ensure
that this type of fraud is not endemic.

</details>

**MKBHD**: 难道不更好的是
直接说这种
欺诈是不可能的。
为什么不说它不可能发生？
为什么不通过实施
实际的技术更改来完全消除它？
<details>
<summary>Original English</summary>

**MKBHD**: - Would it not be even better
to just say this type of
fraud is not possible.
Why not just say it's not probable?
Why not just totally get rid of it
by implementing an
actual technical change?

</details>

**Visa 代表**: 如果你考虑每 100 美元
卡支付的支出。
其中 10 美分是欺诈损失。
所以，每 100 美元是 10 美分。
<details>
<summary>Original English</summary>

**Visa Representative**: - If you think about for every $100
of spend that occurs on card payments.
10 cents of that is lost to fraud.
So, every $100 it's 10 cents.

</details>

**Visa 代表**: 如果你看看面对面交易，
这是这个话题
真正更相关的内容。
每 100 美元的欺诈
这数字下降到 2 美分。
<details>
<summary>Original English</summary>

**Visa Representative**: - If you look at in-person transactions,
which is what kind of this topic
is really much more related to.
That number goes down to 2 cents
for every $100 of fraud that's being made.

</details>

**MKBHD**: 所以，我一直在思考这个黑客技术
它让我想起了很多人
害怕坐飞机。
统计学上讲，你更有可能
在去机场的路上坠机
而不是在空中。
<details>
<summary>Original English</summary>

**MKBHD**: - So, I've been thinking about this hack
and it reminds me a lot about people
who are afraid of flying.
Statistically, you're a lot more likely
to crash on the drive to the airport
than you are in the air.

</details>

**MKBHD**: 所以，我确实理解
Visa 的论点。
与其他类型的欺诈相比，
这只是沧海一粟。
<details>
<summary>Original English</summary>

**MKBHD**: - So, I do understand
Visa's argument generally.
Compared to other kinds of fraud,
this is just a drop in the ocean.

</details>

**MKBHD**: 但航空公司不接受
每年发生的少量坠机
作为做生意的必然成本。
<details>
<summary>Original English</summary>

**MKBHD**: - But airlines don't accept
a small number of crashes each year
as an inevitable cost of doing business.

</details>

**MKBHD**: 不。每次发生坠机，
他们都会仔细分析。
然后他们尽一切努力
确保它
永远不会再发生。
<details>
<summary>Original English</summary>

**MKBHD**: - No. Anytime there's a crash,
they analyze it meticulously.
And then they do everything in their power
to make sure that it's
never gonna happen again.

</details>

**MKBHD**: Visa 说他们会退还你的钱
这很好。
但是你仍然需要注意到这笔账单，
提出异议，然后等待。
<details>
<summary>Original English</summary>

**MKBHD**: - Visa says that they'll
get you your money back
and that's great.
But you've still gotta notice the charge,
dispute it, and then wait.

</details>

**MKBHD**: 想象一下醒来发现
10,000 美元从你的账户消失了。
那是房租、保险、
车贷或医疗账单的钱。
即使退款最终来了，
之前的压力也会非常真实。
<details>
<summary>Original English</summary>

**MKBHD**: - Imagine waking up to see
$10,000 gone from your account.
That's money for rent, insurance,
car payment, or a medical bill.
Even if the refund does come,
the stress before is gonna be very real.

</details>

**MKBHD**: 所以对我来说，问题在于
仅仅说
他们事后会退款是否足够。
或者当一个系统触及
这么多人的生活时，
我们是否应该期待更多？
<details>
<summary>Original English</summary>

**MKBHD**: - So for me, the question
is whether just saying
they're gonna refund it after
the fact is good enough.
Or when a system touches
the lives of so many people,
should we expect better?

</details>

**MKBHD**: 还有最后一件事。
我们被提名为两个 Webby 奖。
一个是我们关于
永远化学品危险的视频
它被提名为最佳长篇视频。
另一个是关于美式橄榄球
我们和 Tom Brady 一起做的，
它被提名为最佳创作者到创作者合作。
<details>
<summary>Original English</summary>

**MKBHD**: - One last thing.
We've been nominated for two Webby Awards.
One, for our video about the
dangers of forever chemicals
and that's been nominated
for best long form video.
The other one is about American football
and we did it with Tom Brady,
and that's been nominated
for Best Creator to Creator Collaboration.

</details>

**MKBHD**: 问题是，当我上次查看时，
我们在这两个奖项中都排在第二名。
所以，如果你想帮助我们，
你可以去 Webby 网站
投票给我们，直到 4 月 16 日。
<details>
<summary>Original English</summary>

**MKBHD**: - The thing is, when I checked last,
we were second place in
voting for both of them.
So if you wanna help us out,
you can go to the Webby website
and vote for us up till April 16th.

</details>

**MKBHD**: 所以如果你这样做，非常感谢。
这将极大地帮助我们。
一如既往，感谢您的观看。
<details>
<summary>Original English</summary>

**MKBHD**: - So if you do that, thank you very much.
That'll help us out a lot.
And as always, thank you for watching.

</details>

**MKBHD**: 好的，是的。这就是整个演示。
我现在会把你的钱还给你。
<details>
<summary>Original English</summary>

**MKBHD**: - Okay, yeah. That's the whole demo.
I will now give you your money back.

</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: - Yes.

</details>

**Henry**: [Henry] 好的，我们得走了。
<details>
<summary>Original English</summary>

**Henry**: - [Henry] Okay, we gotta.

</details>