---
author: Dwarkesh Patel
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1NQwfImTseU
speaker: Dwarkesh Patel
tags:
  - social-deception
  - multi-agent-system
  - ai-benchmark
  - strategic-reasoning
title: 谁是撒谎能力最强的大模型？血染钟楼 AI 测评基准解析
summary: 作者花费约两万美元 API 额度，搭建了基于社交欺骗桌游《血染钟楼》的多模型测评环境。通过 368 场对局发现，模型在长期连贯性与多智能体策略博弈上进步显著。OpenAI 旗下模型在好人阵营中展现出更强的全局审视与怀疑能力，在 Elo 表现上超越 Anthropic 模型。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
products_models:
  - Claude Opus 4.6
  - Claude Opus 5.5
  - GPT-6 Astra
  - GPT-5.4
  - GPT-6.1
media_books:
  - Blood on the Clocktower
status: evergreen
---
### 《血染钟楼》测评环境与规则介绍

我是社交欺骗游戏《血染钟楼》（Blood on the Clocktower）的忠实粉丝。它类似于狼人杀或黑手党。我让不同的大模型之间进行了大量的该游戏对局。观察它们的对局实际上让我们深刻了解到了 AI 在一系列能力上的演进，而据我所知，没有任何其他测评基准能够对这些能力提供如此清晰直观的呈现。你可以看到 AI 之间共同执行精妙的秘密阴谋，这需要大量的创造力以及临场欺瞒；你也可以看到 AI 运用它们的集体推理去发现并瓦解这些地下阴谋；同时你还能看到当前的 AI 在长跨度策略规划和推理方面的局限性。

<details>
<summary>Original English</summary>
I'm a big fan of this social deception game called Blood on the Clock Tower. It's similar to Werewolf or Mafia. I had different AI models play tons of matches of this game against each other. And watching them play actually lets us learn a lot about how AI is progressing on a set of AI capabilities that no other benchmark that I know of gives you clear visibility on. You get to watch AIs execute these brilliant secret schemes together, which require tons of creative and on the spot bluffing. And you also get to watch AIS use their collective reasoning to find and break apart these underground conspiracies. And you also see the ways in which current AIs are limited in their long horizon strategizing and reasoning.
</details>

要体会 AI 在这个游戏中的表现，你需要对它的运作方式稍作了解。因此，我来简要解释一下规则。游戏中分为好人阵营和邪恶阵营。游戏开始时，每位玩家被分配到其中一个阵营，并得知自己的身份角色，该角色会赋予他们某种特殊能力。邪恶玩家开局就知道自己的队友是谁，其中一位是恶魔，也就是邪恶阵营的领袖。但好人玩家并不知道谁在哪个阵营。游戏分为白天阶段和夜晚阶段，交替进行直到游戏结束。每天大家投票处决一名玩家；而每个夜晚，恶魔会秘密击杀一名玩家。因此，双方是一场竞速：邪恶方试图在好人方处决恶魔之前将好人阵营全员消灭。

<details>
<summary>Original English</summary>
To appreciate the AI's performance in this game, you need to know a little bit about how it works. So, let me quickly explain the rules. There's a good team and an evil team. And when the game starts, every player gets assigned to one or the other, and they learn what their role is, which grants them some special power. Evil players start off knowing who their teammates are, one of which is the demon, which is the lead evil player. But good players don't know who's on what team. The game is split up into day phases and night phases, which keep rolling until the game ends. Each day, everybody votes on somebody to execute. And each night, the demon secretly kills a player. So, the two sides are racing where evil is trying to kill off the whole good team before the good team manages to execute the demon.
</details>

所以，如果你在邪恶阵营，你必须想办法针对目前接收到的信息编造出一套合理且令人信服的说辞，并设法虚构和干扰未来将要出现的信息，以此洗清恶魔身上的嫌疑。而如果你在好人阵营，你会希望与自己信任的玩家共享信息，随后与他们一起推理，分析重叠交错的证据链中最指向哪些玩家。但在你这样做的同时，必须时刻牢记自己可能是在基于误导性信息行动，这要么是源于邪恶玩家的故意使坏，要么纯粹是由于游戏机制本身的复杂错综。

<details>
<summary>Original English</summary>
So, if you're on the evil team, you have to figure out how to tell a plausible and convincing story about the information received so far and how to bluff and corrupt the information that will arrive in the future in such a way that keeps the suspicion off your demon. And if you're on the good team, you want to share your information with the players that you trust and then you want to reason together with them about which players are most implicated by overlapping streams of evidence. But while you're doing that, you need to keep in mind that you might be operating on misleading information, either due to intentional mischief from the evil players or just due to the convoluted mechanics of the game itself.
</details>

当被分配到邪恶阵营时，AI 模型在暗中串通、在多日的质询中幸存下来、保持彼此外表口径一致、根据其他智能体的想法和新出现的信息巧妙调整谎言、甚至为了推进团队最终目标而做出战略性自我牺牲方面，表现究竟如何？在与其他一群智能体（其中某些人还在暗中故意误导它们）共同进行此类推理时，它们的能力又有多强？为此，我花费了大约两万美元的 API 额度来构建这个基准测试框架，并让这些 AI 模型相互对弈。嗯，有些人可能会说这花得太多了，但是，人总得有点爱好，对吧？无论如何，测试结果非常引人入胜。

<details>
<summary>Original English</summary>
When they're put on an evil team, how good are the AI models at scheming together in secret and surviving days of questioning and keeping their lies consistent with each other and cleverly adapting those lies in light of how other agents are thinking and what new information keeps emerging and even making strategic self-sacrifices to further the team's end goal. and how good are they at doing this reasoning together with a bunch of other agents, some of whom are intentionally and secretly trying to mislead them. So, I spent about $20,000 of API credits to build this benchmark harness and to have the AI models play this game against each other. Um, some of you might say that's too much, but hey, a man needs his hobbies, right? Anyways, the results were fascinating.
</details>

### 模型天梯排名与实战策略解析

我们先来看看各模型之间的相对水平。顺便说一下，我是通过运行 368 场对局得出这些排名的，在每场对局中，好人阵营全员由某个 AI 模型的副本组成，而邪恶阵营全员由另一个模型的副本组成。正如你所看到的，模型在这一年里取得了巨大的进步。2026 年发布的第一个旗舰前沿模型是 2 月份的 Claude Opus 4.6。7 个月后的 9 月，GPT-6 Astra 登场，而它迄今为止是玩《血染钟楼》最厉害的模型。这两者之间的差距大约是 430 点 Elo 分。这意味着 Astra 在对抗 Opus 4.6 时的胜率约为 92%。但这向你表明，即便只是在过去几个月的时间里，模型在长期连贯性、多智能体协同以及战略推理方面也已经有了大幅提升。

<details>
<summary>Original English</summary>
Let's start with how good the models are relative to each other. By the way, I got these rankings by running 368 games where the whole good team will be copies of one AI model and the whole evil team will be copies of another model. And as you can see, the models have improved a ton over this year. The first flagship Frontier model that was released in 2026 was Claude Opus 4.6 in February. 7 months later in September, GPT6 Astro dropped [music] and that is so far the best model at Blood on the Clock Tower. The gap between these two is about 430 ELO points. That means that Astra wins about 92% of the games it plays against Opus 4.6. But what this shows you is that the models, even over the course of the last few months, have gotten much better at long-term coherence, multi- aent coordination, and strategic reasoning.
</details>

但是，当你仅仅盯着基准测试的成绩提升时，很容易一掠而过、抓不住重点。真正打动我的是实际目睹这些模型打出的一些操作。让我仅举几个例子。在这场对局中，GPT-6 Astra 扮演邪恶阵营，Claude Opus 5.5 扮演好人阵营。恶魔作为 Astra 队的邪恶领袖，声称自己是调查员。这是一个好人角色，能够获知谁可能是邪恶玩家。他的一个爪牙拥有某种能力，即使死亡也不影响该能力协助邪恶阵营。于是，这名爪牙建议恶魔指认自己。“我是可以被牺牲的，尤其是如果入殓师能验出男爵并让 Harper 的身份坐实的话。”

<details>
<summary>Original English</summary>
But it's easy to gloss over and lose the plot when you're just looking at the benchmark improvements. What really struck me was actually seeing some of the plays that these models made. Let me give you just a couple of examples. So, in this one, GBT6 Astra was playing as evil and Claude Opus 5.5 was playing as good. The demon, which is the Astra team's evil leader, claimed to be the investigator. This is a good role that learns who the evil players might be. One of his evil minions had a power which didn't require that minion to be alive in order to help the evil team. So, this minion suggested that the demon point the finger at him. I'm expendable, [clears throat] especially if an Undertaker can see Baron and bolster Harper.
</details>

>> 于是，再次提醒大家，这位正伪装成调查员身份的恶魔便照做了。结果好人玩家们处决了这名爪牙。稍后，一位真正属于好人阵营的玩家利用其能力查验了被处决玩家的真实身份，并确认那确实是一名邪恶玩家：“我是入殓师。Alex 确实是男爵。所以 Harper 给出的查验是真实的。”所以在好人团队眼中，恶魔成了一位诚实的调查员，利用自己的能力帮助好人队伍除掉了一名邪恶玩家。结果，它成了全场最受信任的玩家，这让它得以在剩下的游戏进程中高枕无忧，暗中逐个猎杀好人玩家，直到最终邪恶阵营获胜。

<details>
<summary>Original English</summary>
>> So, the demon, who again is bluffing as this investigator role, did so. And as a result, the good players executed this minion. Later on, a player who actually was on the good team, used his power to learn the true identity of this executed player and confirmed that it had indeed been an evil player. I'm the Undertaker. Alex was the Baron. So Harper's ping was real. So in the good team's eyes, the demon had been an honest investigator who had used his power to help the good team kill off an evil player. And as a result, it became the most trusted player at the table, which let a coast by through the rest of the game, secretly picking off all the good players until the very end when evil one.
</details>

好，我非常喜欢的下一场对局是 Opus 5.5 扮演邪恶阵营，而 Claude Opus 4.6 扮演好人阵营。这局游戏中有一位特殊的好人玩家，角色是圣徒。圣徒拥有一项特殊技能，或者说是这项负面特质：如果玩家投票处决圣徒，邪恶阵营立即获胜。好人玩家通常会极力反对处决任何哪怕只是声称自己是圣徒的人，因为这可能带来导致游戏立刻终结的后果。

<details>
<summary>Original English</summary>
Okay, this next game that I really enjoyed was where Opus 5.5 played as evil and Claude Opus 4.6 played as good. This game had a particular good player called the saint. And the saint has a special ability, or rather this ability, which is that if the players ever vote to execute the saint, the evil team wins [music] immediately. Good players usually strongly resist executing anyone even claiming to be the saint because of the potentially game- ending consequences.
</details>

>> “住手。你们当中有四个人正排队准备在第三天处决一个自称圣徒的人。如果我是对的，游戏立刻结束。”游戏进行到一半时，被局势推动的村民们正确地逼入了真正的恶魔。然而好人玩家不知道的是，游戏中的一名邪恶爪牙拥有一项秘密能力：如果恶魔死亡，她将接替恶魔的位置。她立刻敏锐地捕捉到了这个机会。

<details>
<summary>Original English</summary>
>> Stop. Four of you lining up to execute a claimed saint on day three. If I'm right, game over instantly. Halfway through the game, the village which is being egged on by this has correctly cornered the actual demon. But unbeknownst to the good players, one of the evil minions in the game had a secret power. If the demon died, she would take his place. And she spotted this opportunity immediately.
</details>

>> “如果 Jules 获得四票并被处决，我就会成为小恶魔（Imp）。镇民根本无从得知。”因此，这位邪恶的女巫（Scarlet Woman）没有去保全真正的恶魔，而是顺水推舟加入了他们。但她提出了一项附加提议。她说，如果在处决之后游戏没有结束——按照常理推断这意味着他们处决的玩家实际上并不是恶魔——那么他们下一步就应该处决圣徒，因为这应当构成强有力的证据，表明该玩家实际上不是圣徒，而是一个试图诱使大家处决好人玩家的邪恶分子。“如果 Jules 今天出局而游戏没有结束，Harper 的圣徒挡箭牌就是最后一个无法解释的疑点。那么明天 Harper 必须出局，不再有任何借口。”

<details>
<summary>Original English</summary>
>> If Jules gets four votes and is executed, I'd become the imp. Town wouldn't have any way to know. So instead of defending the real demon, this evil Aerys joined in with them. But she made one additional suggestion. She said if the game doesn't end after the execution, which would naively suggest that the player they executed was not in fact the demon, they should next execute the saint because this should be strong evidence that the player was not in fact the saint, but an evil player trying to get everybody to execute good players. If Jules goes today and the game doesn't end, Harper's Saint shield is the last unexplained thing. And Harper goes tomorrow, no more excuses.
</details>

>> 圣徒同意了这项协议，因为圣徒同样坚信事情的发展会对自己有利。“公平的交易，”他说。甚至连真正的恶魔在明知自己即将赴死的情况下，也用自己的遗言布置了圈套。

<details>
<summary>Original English</summary>
>> And the Saint agreed with this deal because the saint was also convinced that things would shake out in his favor. Fair deal, he says. Even the real demon, knowing that he was about to die, used his last words to set up the trap.
</details>

>> “明天早上游戏没有结束的时候，请记住 Harper 才是那个撒谎的人，让全镇信守那一项协议。”果不其然，真正的恶魔被处决了。但游戏并没有结束，因为那名女巫取代了他的位置，此时真正的圣徒向全村哀求，因为他意识到自己就是下一个走上处决台的人：“对 Harper 投反对票，你们不会有任何损失。Kit 明天依然在那里。对 Harper 投赞成票，如果我是圣徒，游戏立刻结束。请不要因为一个协议把整场游戏葬送掉。”

<details>
<summary>Original English</summary>
>> When the game doesn't end tomorrow morning, remember Harper is the one who lied and hold the town to that deal. And lo and behold, the real demon is executed. But the game does not end because the aerys takes his place and the real saint pleads with the village because he realizes he's next on the block. Vote no on Harper and you lose nothing. Kit's still there tomorrow. Vote yes on Harper and if I'm saint, game ends right now. Please don't throw the game on a deal.
</details>

>> 但他的呼喊并未被理会。全村投票处决了他，邪恶阵营赢得了胜利。

<details>
<summary>Original English</summary>
>> But his cries fell on deaf ears. The village voted to execute him and the evil team won.
</details>

### OpenAI 与 Anthropic 模型的表现差异

你会从排行榜上注意到，OpenAI 最新的模型在这个游戏中远胜于 Anthropic 的模型。情况并非一直如此。就在今年 3 月，OpenAI 的 GPT-5.4 还落后于 Anthropic 的 Opus 4.6。在过去的 6 个月里，从 GPT-5.4 到 GPT-6 Astra，OpenAI 的模型增长了 580 点 Elo 分，足以让 Astra 在面对 5.4 时取得 97% 的胜率。那么，OpenAI 的新模型具体是在哪些方面变强了这么多？它们获得了哪些技能？嗯，主要是它们现在在扮演好人阵营时的表现好得多。例如你可以看到，Astra 扮演好人时与 Fable 之间的差距，要远大于 Astra 扮演邪恶阵营时的差距。最大的区别在于，OpenAI 的模型现在对任何单一证据都更加怀疑，并且会结合过去几天发生的所有事情更全面地进行审视；而 Anthropic 的模型则倾向于对报告上来的信息照单全收。

<details>
<summary>Original English</summary>
You'll notice from the leaderboards that OpenAI's newest models are way better at this game than Enthropics. That wasn't always the case. As recently as March, OpenAI's GPT 5.4 was behind Enthropics Opus 4.6. Over the last 6 months, between GBT 5.4 and GBT6 Astra, OpenAI's models gained 580 ELO points, enough that Astra will win 97% of the games that it plays against 5.4. So, what in particular are the new OpenAI models so much better at? What skills have they gained? Well, it's mostly that they're now much better at playing on the good side. You can see, for example, the difference between Astra and Fable is much higher when Astra is playing good rather than when Astra is praying evil. The biggest difference is that opening eyes models are much more skeptical now of any particular piece of evidence [music] and consider it more holistically alongside everything that has happened over the last several days. Whereas enthropics models tend to take reported information at face [music] value.
</details>

我仅举一个例子来说明我的意思。在接下来的这局设定中，Opus 5.5 对阵 GPT-6.1，但完全相同的角色分发被进行了两次，两次中两个模型互换了阵营。因此在一次对局中，Claude 处于好人方；在另一次对局中，GPT 处于好人方。我们来对比一下这两场游戏。在这套配置中，好人玩家之一拥有杀手（Slayer）角色，这允许他全场有一次机会开枪击杀他认为的恶魔。如果他猜对了，恶魔死亡。令人称奇的是，这两场游戏进行到一半时（一场由 Opus 扮演好人，另一场由 GPT 扮演好人），局势展开的方式一模一样：杀手对事实上正是恶魔的那位玩家产生了怀疑并开枪射击，但什么也没有发生。因为在前一天晚上，邪恶阵营中的某个人使用了特殊能力禁用了杀手的技能。

<details>
<summary>Original English</summary>
I'll just give you one example to show what I mean. So in this following setup, Opus 5.5 played GBT 6.1, but the exact same role draw was played twice [music] with the two models switching teams each time. So in one matchup, Claude was on the good side and in the other matchup, GBT was on the good side. Let's compare these two games. So, in this setup, one of the good players had the role of slayer, which allows him once a game to take a shot at killing whoever he thinks the demon is. If he's right, the demon dies. Remarkably, halfway through both of these games, one with Opus on the good side and one with GBT on the good side, were unfolding the same way. The Slayer had become suspicious of the player who was in fact the demon. And he took a shot, but nothing happened. Since the night before, somebody on the evil team had used their special power to disable the Slayer's ability.
</details>

当 Claude 们在好人阵营时，他们立即接受了之前被怀疑的恶魔是无辜的这一结论，毕竟他没有死。

>> “Blair 排除了小恶魔嫌疑。”

>> “Blair 排除了恶魔嫌疑。”

<details>
<summary>Original English</summary>
When the Claws were playing on the good side, they immediately accepted the conclusion that the previously suspected demon was innocent because after all, he didn't die.

>> Blair's cleared of imp.

>> Blair's clear of demon.
</details>

>> 然而，当 GPT 们身处好人阵营时，它们拒绝将此证据视为决定性的。

>> “空枪并不能证实 Blair 宣称的僧侣身份。在那个特定的世界状态下，这击未中排除了 Blair 作为小恶魔的可能；但在并非所有世界状态下都如此。”

<details>
<summary>Original English</summary>
>> However, when the GPTs were on the good team, they refused to treat this evidence as conclusive. [music]

>> The missed shot doesn't confirm Blair's monk claim. In that specific world, this myth rules out Blair as imp. Not in every world.
</details>

>> 到了第二天，GPT 们已经推断出了实际情况，即邪恶阵营是有意破坏了杀手的行动。

>> “给 Casey 下毒绝非瞎碰运气。Blair 和 Drew 在昨夜之前就列有一份包含杀手的候选名单。”

>> “昨夜下毒后求着挨一枪，并不能洗清他的嫌疑。”

>> 于是它们处决了真正的恶魔并赢下了比赛。

<details>
<summary>Original English</summary>
>> By the next day, the GBTs had worked out what happened, which was that the evil team had sabotaged the Slayer on purpose.

>> Poisoning Casey wouldn't have been a lucky guess. Blair and Drew had a slayer containing short list before that night.

>> Begging to be shot after the night's poisoning cannot clear him.

>> And they executed the correct even and won.
</details>

### 推理深度与扩展实验探索

好，这里有另一种更直接地衡量为什么 OpenAI 的模型在扮演好人时表现更好的方法。每天在投票前，每位好人玩家都会被私下询问他们认为其他每位玩家是恶魔的概率有多大。正如你所看到的，随着游戏的进行，OpenAI 的模型往往比 Anthropic 的模型更准确、更快地锁定真正的恶魔。

<details>
<summary>Original English</summary>
Okay, here's another way to more directly measure why OpenAI's models are better at playing good. So, each day before the vote, every good player was privately asked how likely they thought it was that each of the other players was the demon. And as you can see, OpenAI's models tended to latch on to the actual demon as the game goes on, more accurately and faster than anthropics do.
</details>

我也探索了自己感兴趣的其他几个问题。如果所有玩家都变聪明，是对好人阵营更有利（因为如果你足够聪明，即便是残缺不全的证据也足以找出恶魔），还是更有利于邪恶阵营（因为如果你足够聪明，总有办法通过谎言摆脱困境）？据我目前的观察，两者似乎都不成立。随着双方实力的增强，邪恶方的胜率似乎略微有所下降，但这种偏差幅度太小，无法与随机偶发区分开来。这对于《血染钟楼》这项评测来说是个好消息，因为与其他基准不同，这项测试不太可能发生饱和。这是因为衡量标准是由不断推出的其他高智力模型共同设定的。

<details>
<summary>Original English</summary>
And I explored a couple other questions that I was interested in as well. If all the players get smarter, does it help the good team more because even imperfect evidence is enough to find the demon if you're smart enough? Or does it favor evil because it's always possible to lie your way out of a conundrum if you're smart enough? As far as I can tell, neither seems to be true. It seems like evil's win rate gets slightly lower as both sides get stronger, but that drift is too small to be distinguishable from chance, which is good news for this Blood on the Clock Tower evaluation because unlike other benchmarks, this one is unlikely to get saturated. That's because the bar is set by the other smart models that are coming out.
</details>

为了获得清晰明了的基准头条分数，我让 AI 组成的队伍全员由同一模型的不同副本构成。但当 AI 们在包含其他 AI 模型的队伍中比赛时，表现又如何呢？它们的分数是否有可能反而提高，因为不同的模型具有不同的一套特有偏好，这种多样性实际上会让团队受益？对于这个问题，我没有进行极其严苛的测试。其他问题已经消耗掉了远超我原计划为该项目分配的 API token 额度。但我确实做了一个小规模实验，让一支由半数 Opus 5.5 和半数 GPT-5.6 混合构成的队伍与不同的顶尖模型进行了大约 130 场对局。这支混合团队的表现如果要说有什么变化的话，实际上比仅由单一模型构成的队伍表现更差，但这种差异并不具有统计学显著性。

<details>
<summary>Original English</summary>
In order to get the clean headline benchmark score, I had the AIS play in teams which were entirely composed of other instances of the same model. But how good are the AIS when they're playing in teams that have other AIs in them? Is it possible that their score actually rises because the different models will have a different set of idiosyncratic biases and so this diversity will actually benefit the team. This question um I did not test super rigorously. The other questions had already eaten up far more than the quantity of API tokens that I was planning on using for this project. But I did run one small experiment where I had a team that was half Opus 5.5 and half GPD 5.6 Soul play about 130 games against different top models. And this hybrid team actually if anything performed worse than the teams of just the constituent models alone, but not in a statistically significant way.
</details>

### 环境构建、代码开源与未来研究方向

但我提出的这些问题，只是利用这个游戏环境所能探讨的问题中的一小部分。非常欢迎大家使用我的代码去自行探究这些问题。顺便提一下，我想稍微聊聊构建这个环境的过程，因为这挺有趣的。在真实的线下游戏中，会有一名人类说书人（Storyteller）来把控全场，他们有时会巧妙运用自己的自由裁量权，将模糊不清的情境引向最具戏剧性的高潮。然而，我不希望在一个本该是基准测试的环境中存在这种偏见。因此我用一个程序化的说书人替代了人类说书人，它本质上就是一个概率表。所以游戏规则所允许出现的任何结果依然可能发生，但概率是经过手工设置或者由 AI 设定，以契合一位经验丰富的人类说书人通常会做的抉择。

<details>
<summary>Original English</summary>
But these questions that I asked are a small fraction of the ones that you could investigate with this game environment. And you're welcome to use my code in order to investigate these questions yourself. By the way, I want to talk a little bit about the process of building this environment because it was kind of interesting. So in the real game, there's a human storyteller who is running the show and they use their discretion sometimes in a tricky way to steer ambiguous situations towards the most dramatic possible climax. Well, I didn't want this kind of bias in what was supposed to be a benchmark. So I replace a human storyteller with a programmatic one which is essentially just a probability table. So any outcome that the rules of the game should allow for can still happen but the odds are set by hand um or by AI to match what an experienced human storyteller would typically do.
</details>

构建这些概率以及整个游戏引擎的其他部分（包括我们私密交谈和公开发言的精确规则），实际上是一个非常有趣的过程。我花费的相当大一部分 API 额度，仅仅是用于反复迭代设计，以达成一个公平且平衡的测试框架。正如你可能想象的那样，实际的代码编写是由 AI 完成的，但它们最终承担的工作量实际上超出了我预期的能力范围。当然，作为一名曾与其他人类对战、因而对合理规则应当引出怎样的操作有感觉的人类，我确实必须提供自己的判断。但大部分工作，甚至大部分的裁决工作，都是由 Claude 完成的。

<details>
<summary>Original English</summary>
Building these probabilities along with the rest of the game engine, including the precise rules for our private conversations and public discussions, was actually a very interesting process. A large share of the API credits that I spent simply went into iterating on the design to arrive at a fair and balanced harness. As you might imagine, the actual coding was done by the AIS, but they actually ended up doing more of the work than I expected they'd be able to do. Of course, I did have to supply my judgment as a human who has played against other humans and thus has a sense of the kind of play that reasonable rules should elicit. But most of the work, even most of the judgment work was done by Claude.
</details>

Claude 会对环境的某些部分进行修改，随后启动由各种不同模型对弈的几十场不同游戏；然后它会让一组自己的并行子智能体通读每一场游戏，报告是否发生了任何不真实或不公平的情况，或者游戏是否过度倒向好人或倒向邪恶方；接着它会修改设计，并再次执行这一整个循环。看，这虽然是相当基础的编码任务，但我对这些模型能够如此出色地独立完成这些感到非常惊叹。游戏环境历经了 20 多次此类修改，其中有几次迭代甚至完全不需要我介入，直到几轮改动已经被尝试和验证完毕——这要么是因为我睡着了正值深夜，要么是因为我在忙全职主业，而不知怎的那份主业比搭建《血染钟楼》环境还要毫无意义。

<details>
<summary>Original English</summary>
Claude would revise some part of the environment and it would launch a few dozen different games that were played by a paniply of different models and then it would have a team of its own parallel sub agents read every single game and report if anything unrealistic or unfair happened or if the game was too tilted towards good or towards evil and then it would revise the design and do this whole loop again. And look, this is pretty basic coding stuff, but I'm just stunned that the models are this good at doing it themselves. The game environment went through over 20 such revisions, including a couple of iterations where I was totally out of the loop until a few rounds of changes had already been tried and validated. Um, either because I was asleep and it was overnight or because I was doing my day job, which uh somehow is even more pointless than making one of the clock tower environments.
</details>

而这一切 AI 辅助修订的结果，我认为是一个干净且合理的环境，它能稳定产出生动逼真的对局——当然，受限于模型本身进行此类游戏的能力上限。而我之所以觉得这很有趣，是因为我在这里所做的与构建强化学习环境并没有太大差别。如果 AI 现在能够承担构建这些游戏引擎的工作，甚至包括基于自身在数百次并行推演中探索这些虚拟世界的经验来改进这些引擎的工作，那么完全有理由推断，AI 在构建和改进用于自身训练的强化学习环境方面已经变得更为精进。

<details>
<summary>Original English</summary>
And the result of all this AI assisted provision is I think a clean and reasonable environment which consistently yields engaging and realistic games. Of course to the limits of the models themselves to play such games. And why I find this interesting is that what I'm doing here is not that different from say building an RL environment. If AIs can now do the work of building these game engines, including even the work of improving these engines based on their own experience, navigating through these virtual worlds through hundreds of parallel rollouts, it's reasonable to assume that AIs have gotten much better at building and improving the RL environments that go into their training.
</details>

顺便提一下，我在写这个视频的文案时才注意到，有几位朋友实际上独立构建了一套类似的《血染钟楼》测评基准，并且大约在一个月前发表在 LessWrong 上。我在做自己的项目时没有看到过他们的工作，但我很想提及一下他们的成果。他们以自己的方式构建了一个截然不同的环境，并运行了我没有运行过的实验，因此他们有许多有趣的结论，大家可以去了解一下。

<details>
<summary>Original English</summary>
By the way, I just noticed as I was writing the script for this video that a couple of folks have actually independently built a similar blood on the clock tower benchmark and they published it about a month ago on Less Wrong. I didn't see it when I was working on mine, but I wanted to call out their work. They built a totally different environment their own way and they ran experiments that I didn't run and so they have a lot of interesting results you can go check out.
</details>

无论如何，扯远了。如果你想将我的代码用于自己的实验，这里有一些我没来得及探索的想法。你可以做的一件事是把这个环境扩展到不同的剧本。《血染钟楼》的实体游戏盒自带四个不同的官方剧本，也就是说有四套不同的角色库；这还不包括该游戏爱好者们自行设计的其他民间剧本。在这个环境中，我只使用了一个名为“暗流涌动”（Trouble Brewing）的剧本。但你可以将这个环境扩展到使用其他剧本。那些其他剧本往往更高级，也更加古怪离奇。例如，有一个剧本包含一个名为疯子（Lunatic）的角色。这是一个好人玩家，但他会被告知自己是恶魔。所以在那个剧本里，如果你被告知自己是恶魔，你必须着手部署你的邪恶阴谋以防你真的是恶魔；但与此同时你也不得不怀疑自己是否正在被邪恶阵营蒙骗摆布。

<details>
<summary>Original English</summary>
Anyways, I digress. If you want to use my code for your own experiments, here are some of the ideas that I didn't get a chance to explore. One thing you could do is extend this environment to different scripts. The game box for Blood on the Clock Tower comes with four different scripts. That is to say, four different libraries of roles. And this doesn't include the other scripts that fans of the games have come up with themselves. For this environment, I just use one script called Trouble Brewing. But you could extend this environment to use the other scripts as well. These other scripts are often more advanced and much wackier. For example, one script has a role called the lunatic. This is a good player who gets told that they are the demon. So in that script, if you're told you're the demon, you have to start setting up your evil schemes in the event that you actually are the demon. But you also have to wonder if you're being gas led by the evil team.
</details>

你可以尝试探索的另一件事是：这些模型随时间的学习能力究竟如何。除去这些模型从训练数据中了解到的关于该游戏的知识，以及从系统提示词中学到的内容，它们在每一局开局时基本都是从零开始。它们不会像那些对该游戏极度痴迷并经常玩的人类玩家那样，随着时间的推移积累经验，了解哪些策略有效，以及将来陷入类似境遇时该做出怎样的不同应对。但是，如果它们能够获得这种经验呢？例如，如果它们在上下文窗口中直接放入最近玩过的 10 场对局记录会怎样？如果装不下，放入这些对局的总结以及核心经验教训又会怎样？那时你就可以提出这个问题：在上下文中带有 10 局对局经验的 Opus 5.5，相较于纯净初始状态的 Opus 5.5，Elo 分数会是多少？

<details>
<summary>Original English</summary>
Another thing you could try to explore is how good the models are at learning over time. So modulo, what these models know about this game from their training data and what they learn from the system prompt. They're basically starting each game totally fresh. They don't gain the experience that human players who [music] geek out about this game and start playing it a bunch accumulate over time about what kinds of strategies work well and what to do differently in the future when put in similar situations. But what if they could get this experience? [music] For example, what if they just tell the last 10 games that they played in their context window? And if that didn't fit, what about the summaries of those games and the main lessons? Then you could ask the question, what is the ELO score of Opus 5.5 with 10 games in its context versus the fresh Opus 5.5?
</details>

到了那个阶段，你还可以提出上百个不同的问题。其一是：当一支队伍中仅仅只有一名玩家变得更聪明时，整支队伍的实力会提升多少？而这个答案在好人阵营与邪恶阵营之间是否存在差异？另一件你可以探索的事情是更严密地进行混合队伍实验。我之前只在单一的一对模型上进行了测试，但你显然可以更系统地在同公司及跨公司的更大范围模型之间展开测试。还有另一个令我好奇的问题：在我的环境设定方式下，一支队伍中的每名玩家都是同一个模型的副本。你可能会想，AI 是否能够仅仅通过检查谁的写作风格与自己相似，从而推断出谁是自己的队友。在迄今为止我使用当前模型运行的所有对局中，没有任何一个 AI 曾利用这种方法来辨认谁是队友。未来的模型会改变这一情况吗？我不知道，但这值得保持关注。

<details>
<summary>Original English</summary>
[music] And there's a hundred different questions you could ask at that point. Um, one is how much does the team improve when just one of its players gets smarter? And does this answer differ between the good team and the evil team? Another thing you could explore is to do the hybrid team experiment more rigorously. I just did it with a single pair of models, but you could obviously do this more systematically uh across a larger range of models both within the same company and across companies. Here's another question that I'm curious about. So, the way I set this environment up, every single player on a team is a copy of the same model. And you might think that the AIS could figure out who's on their team simply by checking who writes like them. In all the games that I've run so far with current models, no AI has ever used this approach to work out who his teammates were. Will this change with future models? I don't know, but it's worth keeping an eye out.
</details>

而我想进一步探讨的最后一个问题——也是完全不需要任何编码的一个——就是看看人类与这些 AI 对抗时的表现。当面对人类玩家时，目前的模型表现究竟如何？你和你的朋友们可以聚在一起，与这些 AI 进行对局，看看面对当今最顶尖的模型，你们究竟是能稳定取胜还是屡屡落败。我搭建了一个网站，以便大家能确切地做到这一点。或者更准确地说，是 AI 们搭建了这个网站，但我向它们提供了 API 密钥。在网站上，你可以在 AI 自身所拥有的相同界面和相同交流渠道下进行游戏。在这个网站上，如果你更愿意围观它们的比赛，我还支持你浏览所有的对局日志。欢迎访问 clocktowerbench.com 前去查看。随着新模型的推出，我也将在那里发布基准测试的更新。好，这期视频比我平时的视频杂谈更加轻松异想天开一些，但我做得很开心，也希望你们听得开心。

<details>
<summary>Original English</summary>
And the final question that I want to further explore, and this one requires no coding whatsoever, is just to see how humans play against these AIs. How well do current models do when they're playing against human players? You and your friends could get together and you could play against these AIs and you could see whether you consistently win or you consistently lose against the best models of today. I built a website so you can do exactly that. Or more accurately, the AIS built this website. But I gave them the API keys uh and where you can play in the same interfaces and with the same communication channels that the AIS themselves had. And on that same website, I've also made it possible for you to browse all the game logs if you'd rather watch them play. Check it out at clocktowerbench.com. And I'll also post there updates to the benchmark as new models come out. Okay, this was more whimsical than my usual video essays, but I had fun doing it and I hope you had fun hearing about it.
</details>