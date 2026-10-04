---
author: Veritasium
date: '2026-06-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=tz23G_UXCGA
speaker: Veritasium
tags:
  - gps-jamming
  - electronic-warfare
  - satellite-navigation
  - radio-frequency
  - missile-warning-system
title: 欧洲上空的GPS干扰：探秘俄罗斯卫星的电子战能力
summary: 2019年起，欧洲GPS信号出现不明干扰，经德克萨斯大学研究员追溯，确认为俄罗斯Cosmos 2546系列卫星所为。干扰事件短促且集中在欧洲工作时间，表明这可能是俄方电子战能力的周期性测试，对全球导航系统构成潜在威胁。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Todd Humphreys
  - Zach Clements
companies_orgs:
  - University of Texas at Austin
  - German Aerospace Center
products_models:
  - GPS
  - GNSS
  - Cosmos 2546
  - Molniya orbit
  - BeiDou
  - eLoran
media_books: []
status: evergreen
---
### 欧洲GPS信号神秘中断

**旁白**: 2024年11月，**德克萨斯大学奥斯汀分校**的GPS专家**托德·汉弗莱斯教授**收到一个神秘线索：查看几年前由GPS监测站网络收集的数据集中，在两个特定日期的精确时间。这些监测站持续记录卫星导航系统的信号，测量它们相对于背景噪声的强度。这看起来并不乐观。这些数据来自2021年，并且是公开可用的。因此，如果其中有任何异常，肯定有人已经发现了。但是**汉弗莱斯教授**和他的学生**扎克·克莱门茨**在建议的两个特定时间检查了数据，他们发现了一些令人惊讶的事情。在一个精确的时刻，整个网络的接收器都报告了同一件事，即信噪比突然下降。实际上，导航信号被压制了。测得的信噪比下降了大约10倍。但当他们开始回顾数据时，他们发现在2019年以来有75天发生了这种强烈的干扰。而且，这种模式一次又一次地出现：所有这些接收器都在同一时间记录了相同的下降。

<details>
<summary>Original English</summary>

**In November 2024**: Professor Todd Humphreys, a GPS expert at the University of Texas at Austin, got a mysterious tip-off. Look at two specific days, at exact times in a data set collected years earlier by a network of GPS monitoring stations. These stations continuously record signals from satellite navigation systems, measuring how strong they are relative to background noise. It didn't seem promising. The data was from 2021, and it was publicly available online. So surely if something unusual was in there, someone would have already found it. But Professor Humphreys and his student Zach Clements looked into the data at the two specific times suggested, and they discovered something surprising. At one precise moment, receivers across the network all reported the same thing, a sudden drop in signal-to-noise ratio. In effect, the navigation signals had been overwhelmed. The measured signal-to-noise dropped by roughly a factor of 10. But when they started looking back through the data, they found 75 days since 2019 where these strong disruptions had taken place. And again, and again, the pattern was the same. All these receivers recorded the same drop at the same time.

</details>

**托德·汉弗莱斯**: 这种效应在整个欧洲都能感受到，北至**斯瓦尔巴群岛**，南至**西班牙**，西至**加拿大**，东至**波兰**东部。事实上，它在欧洲呈现出独特的模式，看起来爆发中心在**波兰**或**加里宁格勒**地区。

<details>
<summary>Original English</summary>

**Todd Humphreys**: This effect was being felt all the way across Europe, all the way to the north, to Svalbard, to the south, to Spain, all the way to Canada in the west, as far east as eastern Poland. And in fact, it had a distinct pattern across Europe to where it looked like the blast center was in Poland or Kaliningrad in that area.

</details>

### 干扰源的初步猜测

**旁白**: 那么，他们想知道是什么导致了这一切。起初，他们认为这可能是干扰，地面上的某种东西发出了更强的信号，淹没了来自卫星的信号，这使得**加里宁格勒**成为一个有趣的候选。它是一个高度军事化的**俄罗斯**飞地，位于波罗的海，夹在**波兰**和**立陶宛**之间。近年来，它已成为这种电子战的热点。所以，也许就是这样，是该地区冲突的副作用。但他们意识到这种解释行不通。

<details>
<summary>Original English</summary>

**Host**: So, they wondered what could cause this. At first, they thought perhaps it's interference, something on the ground broadcasting a much stronger signal, drowning out the ones coming from the satellites, which made Kaliningrad an interesting candidate. It's a heavily militarized Russian exclave on the Baltic Sea wedged between Poland and Lithuania. And in recent years, it's become a hotspot for this kind of electronic warfare. So maybe that was it, a side effect of the conflict in the region. But they realized that explanation didn't work.

</details>

**托德·汉弗莱斯**: 即使是**加里宁格勒**最高的塔楼，也只能影响到**丹麦**等地的航空。所以，我们遇到了一个谜团。我们有过被称为局部干扰的经验，比如塔楼上的东西，或者飞机上的东西，可能会覆盖数百公里。但这不同。这是洲际规模的。

<details>
<summary>Original English</summary>

**Todd Humphreys**: Even the highest tower in Kaliningrad only affects aviation as far as, say, Denmark. So, we had ourselves a mystery on our hands. We were experienced with interference that you could call local, something on a tower, something on a plane that might cover hundreds of kilometers. But this was different. This was continental scale.

</details>

### 排除地面干扰源

**旁白**: 研究人员绘制出所有受影响的站点，并提出了一个简单的问题。什么样的源能同时影响所有这些站点？地面源根本行不通。地球的曲率会在这些距离上阻挡信号。同时影响如此广阔区域的唯一方法是来自地球高空。即使采用最保守的假设，即源只需要从每个站点的角度刚好看清地平线，几何学显示它必须在至少**1200公里**高处。这比**国际空间站**还要高得多。那么，是什么导致了这一切呢？好吧，太空中有一个已知的射电干扰源，那就是太阳。2025年11月，一场主要的**太阳风暴**在全球范围内扰乱了GPS定位长达数小时。那么，这些干扰事件会是太阳引起的吗？当然存在疑问。太阳干扰通常会在几十到几百秒内增强和减弱。但这些事件是突然的，只有三到五秒的短促爆发。另一个重要线索是受干扰的频率。太阳干扰通常涵盖广泛的无线电频率范围，而这种干扰仅限于一个非常窄的频段，只有**5兆赫**宽，中心频率为**1577.5兆赫**。这恰好是GPS使用的频谱部分。最后的决定性证据是，太阳射电爆发会影响地球整个日照面。但研究人员在这里看到的情况更为集中，始终集中在**欧洲**上空。

<details>
<summary>Original English</summary>

**Host**: The researchers mapped out all the stations that were affected and asked a simple question. What kind of source could have affected all of them at once? The source on the ground just wouldn't work. The curvature of the earth would block the signal over these distances. The only way to affect such a wide area simultaneously is from high above the earth. And even using the most conservative assumptions, that the source only has to just clear the horizon from the perspective of every station, the geometry shows it had to be at least 1,200 kilometers up. That's way higher than the International Space Station. So, what was causing this? Well, there is one known source of radio interference from space, which is the sun. In November 2025, a major solar storm disrupted GPS positioning globally for several hours. So, could these interference events be caused by the sun? There were certainly question marks. Solar interference typically builds up and fades over tens to hundreds of seconds. But these events were abrupt, short bursts of only three to five seconds. Another important clue was the frequencies that were disrupted. Solar interference typically spans a wide range of radio frequencies, whereas this interference was confined to a very narrow slice, just five megahertz wide, centered at 1,577.5 megahertz. That's right in the part of the spectrum used by GPS. And the final nail in the coffin is that solar radio bursts affect the entire sunlit side of the earth. But what the researchers were seeing here was much more concentrated, consistently centered over Europe.

</details>

### 卫星：唯一的合理解释

**旁白**: 所以，托德和扎克意识到唯一能引起这一切的只能是一颗卫星，这只剩下一个问题：

<details>
<summary>Original English</summary>

**Host**: So, Todd and Zach realized the only thing that could be causing this was a satellite, which left them with just one question.

</details>

**托德·汉弗莱斯**: 是故意的还是意外的？我和我的学生都认为这前所未有。我们以前从未见过这种情况。全世界也从未见过。

<details>
<summary>Original English</summary>

**Todd Humphreys**: Is it intentional or is it accidental? Both my student and I looked at this and said, unprecedented. We've never seen this before. The world has never seen this before.

</details>

**旁白**: 这颗卫星似乎在针对**GPS**。或者更确切地说，我们大多数人称之为**GPS**的。这只是简称。**GPS**是**美国**的系统，但还有其他系统，包括**俄罗斯**的、**欧洲**的和**中国**的。你的手机实际上会使用这些卫星中的许多来告诉你你在哪里。这些系统被称为**全球导航卫星系统**或**GNSS**。当**美国军方**在1970年代首次开发该系统时，他们想证明它到底有多好用。因此，**GPS项目办公室**给自己设定了一个雄心勃勃的目标：使用**GPS**从一架移动的飞机上连续投放五枚炸弹到同一个孔中。

<details>
<summary>Original English</summary>

**Host**: This satellite seemed to be targeting GPS. Or rather what most of us call GPS. That is just the shorthand. GPS is the American system, but there are others, including the Russian one, the European one, and the Chinese one. And your phone is actually of these satellites to try and tell you where you are. These systems are known as Global Navigation Satellite Systems or GNSS. And when the U.S. military first developed the system in the 1970s, they wanted to prove how well it really worked. So, the GPS program office set itself an ambitious goal to use GPS to drop five bombs in a row into the same hole from a moving plane.

</details>

**托德·汉弗莱斯**: 他们在炸弹将要落入的地方旁边放了一把椅子。等等，什么？如果有人怀疑我们能把炸弹投进同一个洞里，欢迎你站到那里看着。

<details>
<summary>Original English</summary>

**Todd Humphreys**: They set up a chair next to the site that the bombs are going to be going into. Wait, what? If anyone doubts that we can drop the bombs in the same hole, you're welcome to go and stand right there and watch out.

</details>

### GPS工作原理揭秘

**旁白**: 那么**GPS**是如何工作的呢？想想你的手机为了告诉你你在哪里实际做了什么。它在监听来自卫星的信号。这些信号可以告诉它两件事。首先，卫星在太空中的位置。其次，信号发送的精确时间。然后接收器可以将这与信号到达的时间进行比较。你可以使用这个时间差，乘以光速，你就得到了距离。所以，如果信号花费了0.07秒，那意味着你离卫星大约**21000公里**。如果你只使用一颗卫星，那会将你定位在它周围的一个巨大球体上的某个位置。现在你可以添加第二颗，那会将你的位置缩小到两个球体相交的这个圆圈。如果你添加第三颗，你将把它缩小到只有两个可能的点。而其中只有一个实际上在地球表面。所以你可能认为三颗卫星就足够了。我们有三个方程，每个卫星一个，以及三个未知数，分别是我的位置x、y和z。所以，在左边，我有我与三颗卫星之间几何距离。在右边，我有测得的信号时间，都乘以光速。

<details>
<summary>Original English</summary>

**Host**: So how does GPS work? Well, think about what your phone is actually trying to do to tell you where you are. It's listening to signals from satellites. And those signals can tell it two things. First, the position of the satellite in space. And second, the exact time the signal was sent. And then the receiver can compare that to when the signal arrives. And you can use that time difference, multiply it by the speed of light, and you get the distance. So, if it took the signal 0.07 seconds, that must mean you're around 21,000 kilometers away from the satellite. If you're only using a single satellite, that puts you somewhere on a huge sphere around it. Now you can add a second one, and that will narrow your position down to this circle where the two spheres intersect. If you add a third, you will narrow it down to only two possible points. And only one of these is actually on Earth's surface. So, you might think three satellites is all you need. We have three equations, one for each satellite, and three unknowns that are my position, x, y, and z. So, on the left side, I have the geometric distance between me and each of the three satellites. And on the right side, I have the measured signal time, all multiplied by the speed of light.

</details>

**托德·汉弗莱斯**: 卫星有原子钟，所以它们的计时漂移每百万年只有三秒。但我的手机没有原子钟，所以它的时钟可能在几天内就漂移那么多。仅仅**100纳秒**的计时误差就会使你的位置偏离**30米**。所以，实际上，每个距离都略有误差，这意味着你计算出的位置也略有偏差。所以现在，我不仅要解决位置问题，还要解决时钟误差问题。我们称之为b。但是现在我有三个方程和四个未知数，这是无法解决的。所以，我可以通过添加第四个方程或第四颗卫星来解决这个问题。四个方程，四个未知数，这使得系统可解。

<details>
<summary>Original English</summary>

**Todd Humphreys**: Now, satellites have atomic clocks, so their timing drifts by only three seconds every million years. But my phone does not contain an atomic clock, so its clock can drift by that much in just a couple of days. And a timing error of just 100 nanoseconds throws off your position by 30 meters. So, in reality, each distance is slightly wrong, which means the position you calculate is slightly off too. So now, instead of just solving for position, I also have to solve for the clock error. So, let's call that b. But now I have three equations and four unknowns, which is unsolvable. So, I can fix that by adding a fourth equation or a fourth satellite. Four equations, four unknowns, that makes the system solvable.

</details>

### 地面站与类星体：定位的终极参考

**旁白**: 好的，但我们做了一个关键假设，那就是当我计算我的位置时，我知道卫星在哪里。当然，它可以告诉我它在哪里，但它绕地球的位置和速度 constantly changing。那么卫星到底是如何知道自己在哪里的呢？

<details>
<summary>Original English</summary>

**Host**: Okay, but we've made one key assumption, that when I'm calculating my position, I know where the satellite is. And sure, it can tell me where it is, but its position around the Earth and its speed are constantly changing. So how does the satellite actually know where it is in the first place?

</details>

**拉姆齐**: **GPS卫星**需要被告知它们在哪里，而它们是通过监测它们的地面站被告知在哪里的。地面站必须知道它们在哪里才能告诉卫星它们在哪里。

<details>
<summary>Original English</summary>

**Ramsey**: The GPS satellites need to be told where they are, and they're told where they are with ground stations that monitor them. And the ground stations have to know where they are to tell the satellites where they are.

</details>

**格雷戈**: 但地球本身随着大陆的移动而不断变化。

<details>
<summary>Original English</summary>

**Gregor**: But the Earth itself is constantly shifting as the continents move.

</details>

**拉姆齐**: 那么我们如何确定地面站的位置呢？你通过**类星体**来确定地面站的位置。

<details>
<summary>Original English</summary>

**Ramsey**: So, how do we work out where the ground stations are? You work out using quasars where the ground stations are.

</details>

**格雷戈**: 因为它们距离数十亿光年，**类星体**在夜空中看起来几乎是完全固定的，这意味着我们可以将它们用作参考点，就像早期探险家通过星星导航一样。一小部分**类星体**是极其明亮的射电源。当这些无线电波到达地球时，世界各地的望远镜会在略微不同的时间检测到它们。从这些微小的到达时间差异中，你可以精确地确定望远镜的相对位置。通过长时间进行大量测量，你可以建立一个精确的地球自身移动（包括大陆）的地图。**GPS地面站**与同一张地图相连。

<details>
<summary>Original English</summary>

**Gregor**: Because they're billions of light years away, quasars appear almost perfectly fixed in the night sky, which means we can use them as reference points, much like early explorers navigating by the stars. A small fraction of quasars are extremely bright radio sources. When those radio waves reach Earth, telescopes around the world detect them at slightly different times. From those tiny differences in arrival time, you can precisely determine the relative position of the telescopes. And by making lots of those measurements over time, you can build a precise map of how the Earth itself moves, continents included. GPS ground stations are tied into that same map.

</details>

**拉姆齐**: 地面站告诉卫星它们在哪里，然后你就是这样确定你在哪里的。

<details>
<summary>Original English</summary>

**Ramsey**: The ground stations tell the satellites where they are, and then that's how you work out where you are.

</details>

**格雷戈**: 你简直让我大开眼界。

<details>
<summary>Original English</summary>

**Gregor**: You just blew my mind.

</details>

**拉姆齐**: 所以，我们总是通过**GPS**，通过星星导航。

<details>
<summary>Original English</summary>

**Ramsey**: So, we're always navigating by the stars, just via GPS.

</details>

### 影响GPS精度的各种因素

**旁白**: 实际上，你的手机不仅仅连接到四颗卫星。通常远不止这些。我的手机现在正在使用超过**20颗卫星**。那是因为系统做的远不止解决四个方程。假设你在**巴黎**的一条小街上，你打开地图试图找出你在哪里。结果发现有很多事情会影响这一点。有一些相对简单的，比如考虑**狭义相对论**和**广义相对论**。如果你不纠正这一点，你的位置每天会漂移大约**11公里**，你可能在整个区域的任何地方。所以，卫星不断被监测和更新，它们发送**时间校正**，你的手机会实时应用。现在，除此之外，在信号到达你的那一小段时间里，地球实际上已经稍微旋转了。所以，当你的手机确定你在哪里时，它还必须考虑信号发送时**巴黎**在哪里，而不是现在在哪里。如果你不纠正这一点，会增加大约**20米**的误差，足以让你不在同一个街区。当然，信号必须穿过地球大气层。现在，**电离层**会为你的位置增加**5到15米**的误差，而大气层的较低层，由于天气、压力和湿度，会再增加一到两米。所以，如果你不考虑这些，你仍然会在街道的错误一边。这就是额外卫星派上用场的地方。它们为你的手机提供额外的测量值，以分离误差，并更好地确定你的位置。所以最终，它可以精确到**3到5米**，如果你考虑到解决这个问题需要什么，这是相当不可思议的。而使用最先进的**GNSS技术**，你可以将其进一步推进到几厘米。但此时，你实际上必须开始考虑**重力如何弯曲时空**并延迟信号之类的事情。

<details>
<summary>Original English</summary>

**Host**: And in reality, your phone isn't connected to just four satellites. It's usually far more than that. Mine right now is using, it's like over 20 satellites. That's because the system is doing much more than just solving for four equations. Say you're on this little street in Paris and you open maps and you try to figure out where you are. Turns out there are a lot of things that can throw this off. There's the relatively simple ones, like taking into account special and general relativity. If you didn't correct for that, your position would drift about 11 kilometers per day, and you can be anywhere within this entire area. So, the satellites are constantly being monitored and updated, and they send down timing corrections that your phone applies in real time. Now, on top of that, in the fraction of a second that it takes for the signal to reach you, the Earth has actually rotated slightly. So, when your phone figures out where you are, it also has to account for the fact where Paris was when the signal was sent, not where it is now. If you don't correct for that, that adds about 20 meters of error, enough that you're not even on the same block. And of course, the signal has to pass through Earth's atmosphere. Now, the ionosphere will add between 5 and 15 meters of error to your position, and the lower levels of the atmosphere, with weather and pressure and humidity, will add another meter or two. So, if you don't account for that, you'll still be on the wrong side of the street. And that's where the extra satellites come in handy. They give your phone extra measurements to separate out the errors and give you a better fix of your position. So ultimately, it can be accurate down to 3 to 5 meters, which is pretty incredible if you think about what it takes to solve this. And with the most advanced GNSS tech, you can push this even further to a few centimeters. But at this point, you actually have to start accounting for stuff like how gravity bends space-time and delays the signal.

</details>

### GPS信号的脆弱性

**旁白**: 但所有这些只有在你真的能听到那些信号时才有效。

<details>
<summary>Original English</summary>

**Host**: But all of this only works if you're actually able to hear those signals.

</details>

**拉姆齐**: 当信号从太空到达时，它已经传播了**20000公里**才到这里，而且它只用大约**50瓦**的功率传输。所以，它就像一个两倍地球直径距离远的旧式灯泡。

<details>
<summary>Original English</summary>

**Ramsey**: When the signal arrives from space, it's traveled 20,000 kilometers to get here, and it was only transmitted with about 50 watts of power. So, it's like an old school light bulb two Earth diameters away.

</details>

**格雷戈**: 而且因为这种功率在如此巨大的距离上传播开来，你的手机接收到的**GPS信号**只有**十万亿分之一瓦**，或者说**10的负16次方瓦**。

<details>
<summary>Original English</summary>

**Gregor**: And because that power spreads out over such a vast distance, the received GPS signal at your phone is only about a tenth of a quadrillionth of a watt, or 10 to the negative 16 watts.

</details>

**拉姆齐**: 它非常安静。

<details>
<summary>Original English</summary>

**Ramsey**: It's insanely quiet.

</details>

**旁白**: 这意味着它很容易被淹没。如果你在相同的频率上广播足够的噪声，你就可以压制信号，直到它与背景噪声无法区分。这被称为**干扰**。许多这些导航系统使用大致在**1.1到1.6吉赫兹**之间的无线电频谱。较低频率的信号能很好地穿透大气层，但需要更大的天线。较高频率的信号允许使用更小的天线，但信号更容易被吸收和散射，尤其是在恶劣天气下。所以，这个频段是一种导航系统所依赖的最佳选择。这意味着如果有什么东西干扰了它，它可能同时影响多个系统。这就是为什么这部分频谱受到严格保护的原因。不应该有其他东西在这里传输。故意干扰这些信号在大多数国家都是非法的，但却有东西在这样做。一个强大到足以压制整个大陆的卫星导航的强大东西。这又回到了托德·汉弗莱斯教授面临的问题。这是意外吗？还是有人故意泛滥这个频段？

<details>
<summary>Original English</summary>

**Host**: Which means it doesn't take much to drown it out. If you broadcast enough noise at the same frequency, you can overwhelm the signal until it becomes indistinguishable from the background. This is called jamming. And a lot of these navigation systems use the radio spectrum, roughly between 1.1 and 1.6 gigahertz. Lower frequencies travel well through the atmosphere, but they require much larger antennas. Higher frequencies allow for smaller antennas, but the signals are much more easily absorbed and scattered, especially in bad weather. So, this band is a kind of sweet spot that navigation systems rely on. Which means if something interferes with it, it can affect multiple systems at once. That's why this part of a spectrum is tightly protected. Nothing else is supposed to be transmitting here. And deliberately interfering with these signals is illegal in most countries, but something was. Something powerful enough to overwhelm satellite navigation across an entire continent. Which brings us back to the question facing Professor Todd Humphreys. Was this accidental? Or was someone flooding this band on purpose?

</details>

### 干扰行为的时序性分析

**托德·汉弗莱斯**: 这就像一本悬疑小说，你在试图找出是不是管家在厨房里用撬棍杀了人，对吧？我们必须把所有的线索拼凑起来。如果它是随机发生的，因为卫星的某种故障，也许某个放大器过热并出现故障，那么你会期望它在周一和周五发生的可能性是相同的，对吧？

<details>
<summary>Original English</summary>

**Todd Humphreys**: It's, you know, a mystery novel here where you're trying to figure out whether it was the butler in the kitchen with the crowbar, right? And we have to put all of the clues together. If it had been random, occurring because of some failure in a satellite, maybe some amplifier gets too hot and misbehaves, then you'd expect it to happen equally likely on a Monday and a Friday, right?

</details>

**旁白**: 但当他们回顾数据时，出现了一些奇怪的事情。干扰事件主要发生在**欧洲**的工作时间，即周二、周三和周四。

<details>
<summary>Original English</summary>

**Host**: But when they went back through the data, something strange emerged. The interference events were happening mostly on Tuesdays, Wednesdays and Thursdays during business hours in Europe.

</details>

**托德·汉弗莱斯**: 那么，告诉我，有什么放大器会在**欧洲**的周三工作时间出现故障呢？

<details>
<summary>Original English</summary>

**Todd Humphreys**: So, tell me, tell me what amplifier tends to fail during business hours in Europe on Wednesdays.

</details>

**旁白**: 所以现在我们知道这可能不是随机的。很可能有人为因素。但这不一定意味着它是故意的或恶意的。所以，搜寻实际来源的工作开始了。但这比你想象的要困难。因为仍然有太多的未知数。在这种情况下，不确定性很快就会变成相互竞争的叙述。我们以前见过。当**欧盟**领导人的飞机去年 allegedly 受到**GPS干扰**时，超过**150家新闻媒体**对此进行了报道。但根据你在哪里看到这个故事，你的看法可能完全不同。如果你先看到《**世界报**》，你可能会认为这可能是**俄罗斯**的错。如果你先看到《**新闻周刊**》，你肯定会认为那是**俄罗斯**。如果你看到这个标题，好吧，你可能会质疑这个故事的真实性。三个标题，三个完全不同的结论。这就是为什么我们今天使用赞助商**Ground News**。他们是一个网站和应用程序，旨在让阅读新闻更简单、更数据驱动。每天他们都会从世界各地拉取数千个故事。每个故事都附带政治倾向、真实性评级和所有权的可视化细分。所有这些都由三个独立的媒体监测组织进行评级支持。让我们回到那个故事看看它的实际应用。

<details>
<summary>Original English</summary>

**Host**: So now we know this probably isn't random. There's likely human input. But that doesn't necessarily mean it's intentional or malicious. So, the hunt was on to track down the actual source. But that turned out to be harder than you might think. Because there were still so many unknowns. In situations like this, uncertainty can quickly turn into competing narratives. We've seen it before. When the EU chief's plane was allegedly hit by GPS interference last year, over 150 news outlets reported on it. But depending on where you saw the story, your perception could be completely different. If you saw Le Monde first, you might have come away thinking it might be Russia's fault. If you saw Newsweek first, you would definitely think it was Russia. And if you saw this headline, well, you might question the veracity of the story altogether. Three headlines, three entirely different conclusions. That's why we use today's sponsor Ground News. They're a website and app designed to make reading the news easier and more data-driven. Every day they pull in thousands of stories from around the world. And each story comes with visual breakdowns of political leaning, factuality rating and ownership. This is all backed by ratings from three independent media monitoring organizations. Let's go back to that story to see it in action.

</details>

### 排除嫌疑卫星

**旁白**: 立刻，你可以看到超过**150家新闻媒体**报道了这个故事。在这下面，你可以看到报道在政治光谱上分布相对均匀。再往下，你可以查看总体真实性和所有权。甚至可以看到谁率先报道了新闻。他们甚至有一个偏见比较功能，突出文章内容中的具体差异。我最喜欢的功能之一是他们的**盲点动态**，它向你展示了被政治光谱一方或另一方低估的故事。获取准确信息以保持知情已成为一项全职工作。但这正是**Ground News**如此有价值的原因。他们的数据驱动方法有助于让每个人在几分钟而不是几小时内轻松获取和消化信息。所以，如果你和我们一样关心真相，请访问ground.news/VE或扫描这个二维码。我们的链接可以让你在他们的**Vantage计划**上获得**40%的折扣**。所以，我要感谢**Ground News**赞助本视频的这一部分。现在，回到搜寻来源。

<details>
<summary>Original English</summary>

**Host**: Right away, you can see that over 150 news outlets reported on the story. Below that, you can see that coverage was split relatively evenly across the political spectrum. And below that, you can check the overall factuality and ownership. Even see who broke the news. They even have a bias comparison feature that highlights specific differences in the contents of the articles. One of my favorite things is their blind spot feed, which shows you stories that are underreported by one side of the political spectrum or the other. Staying informed with accurate information has become a full-time job. But that's what makes Ground News so valuable. Their data-driven approach helps make information accessible and digestible for everyone in minutes rather than hours. So, if you, like us, care about getting to the truth, go to ground.news/VE or scan this QR code. Our link gets you 40% off their vantage plan. So, I wanna thank Ground News for sponsoring this part of the video. And now, back to the hunt for the source.

</details>

**托德·汉弗莱斯**: 为此，我们必须建立一种复杂的估计问题，但存在许多未知数。

<details>
<summary>Original English</summary>

**Todd Humphreys**: To do this, we have to set up a kind of elaborate estimation problem, but there are many unknowns.

</details>

**旁白**: **干扰器**通过在相同频段广播更强的信号来工作。这有点像对着低语的人大喊大叫。所以，如果这是一个地面干扰器，你可以通过观察信号强度来追踪它。你越靠近，信号就越强。但一旦你处理的是太空中的东西，这种直觉就失效了。要从信号强度反推，你需要知道卫星传输了多少功率，以及其波束的精确形状和方向。甚至每个接收器的天线如何响应来自不同角度的信号。在地球上方**1200公里**处，非常不同的卫星位置可以产生几乎相同的地面模式。所以，研究人员没有直接尝试精确定位发射器，而是使用了更简单的过滤器。如果一颗卫星同时在所有这些站点造成干扰，那么它必须同时在所有这些站点的地平线之上。目前，轨道上有超过**15000颗活跃卫星**。但这个限制让你排除了超过**98%**的卫星。这仍然留下大约**200种可能性**。剩下的是处于非常高轨道的卫星，其中许多在或接近**地球同步带**，它们以与地球旋转相同的速度移动，因此它们停留在一点上方。从大约**36000公里**高空，一颗卫星可以同时看到地球的巨大一部分。然而，如果同一颗卫星在不同日期造成了多次事件，那么它每次都必须满足这个条件，这将其缩小到只有**14个可能的嫌疑**。

<details>
<summary>Original English</summary>

**Host**: A jammer works by broadcasting a stronger signal in the same frequency band. It's kind of like yelling over someone whispering. So, if this were a jammer on the ground, you could track it down by looking at signal strength. The closer you are, the stronger the signal will get. But once you're dealing with something in space, that intuition breaks down. To work backwards from signal strength, you'd need to know how much power the satellite was transmitting, and the exact shape and direction of its beam. Even how each receiver's antenna responds to signals arriving from different angles. And at 1,200 kilometers above the Earth, very different satellite positions can produce almost identical patterns on the ground. So instead of trying to pinpoint the transmitter directly, the researchers used a simpler filter. If a satellite caused interference at all these stations at the same time, then it had to be above the horizon for all of them at once. Right now, there are over 15,000 active satellites in orbit. But that one constraint lets you eliminate over 98% of them. That still leaves around 200 possibilities. What's left are satellites in very high orbits, many of them in or near the geostationary belt, where they move at the same rate as the Earth rotates, so they stay fixed over one point. From about 36,000 kilometers up, a single one can see a huge portion of the Earth at once. However, if the same satellite caused multiple events on different days, then it has to satisfy that condition every single time, which narrows it down to just 14 possible suspects.

</details>

**托德·汉弗莱斯**: 那么，这14颗卫星中包含了哪些类型的卫星和国家呢？

<details>
<summary>Original English</summary>

**Todd Humphreys**: So, what kind of satellites and countries were in these 14?

</details>

**旁白**: 嗯，有几个有趣的候选者。其中一颗是**阿尔及利亚**运营的卫星，它甚至在公开文档中有一个与我们看到的干扰频段相同的发射器。

<details>
<summary>Original English</summary>

**Host**: Well, there were several interesting candidates. One was a satellite operated by Algeria, and it even had, on public documentation, a transmitter in the same frequency band we were seeing interference on.

</details>

**旁白**: 所以，他们仔细检查了一下，从纸面上看它符合。它对所有参考站都可见，并且可以在他们看到的频段内传输。这看起来可能是答案。但他们有一个挥之不去的疑虑，即在**斯瓦尔巴群岛**和**格陵兰西部**最远的一些站点，这颗卫星几乎在地平线之上，这意味着如果它是来源，信号就必须掠过地球，几乎只是擦过这些接收器的天线。现在，这并非不可能。低角度信号可以被接收到，但研究人员看得越多，他们就越不确定这颗卫星是否真的是来源。所以，他们检查了在干扰事件期间跟踪这颗卫星的**GNSS接收器**的数据。

<details>
<summary>Original English</summary>

**Host**: So, they took a closer look, and on paper it fit. It was visible to all of the reference stations, and it could transmit in exactly the band they were seeing. This looked like it could be the answer. But they had a nagging doubt that some of the most distant stations in Svalbard and western Greenland, this satellite was barely above the horizon, which meant if it was the source, the signal would have to be skimming across the Earth and just barely glancing into the antenna of these receivers. Now, that's not impossible. Low angle signals can be picked up, but the more researchers looked, the less certain they became that this satellite was actually the source. So, they examined data from GNSS receivers that were tracking this satellite during the interference events.

</details>

**托德·汉弗莱斯**: 它看起来就像所有其他普通的**GPS信号**一样，被这种干扰猛烈冲击。所以，信号功率与背景噪声的比率也下降了，并且下降的比例与同时其他**GPS信号**下降的比例相同。这并非攻击者。这只是**L波段**中另一个合法的信号，受到了干扰。

<details>
<summary>Original English</summary>

**Todd Humphreys**: It looked just like all of the other ordinary GPS signals that were getting hammered by this interference. So, the ratio of the signal power to the background noise also dropped and dropped in the same proportion that the other GPS signals were dropping at the same time. This was not the attacker. This was just another legitimate signal in the L band that had been interfered with.

</details>

**旁白**: **阿尔及利亚卫星**不是来源。它是另一个受害者。但其他13颗卫星呢？其中任何一颗都可能同时对所有站点可见。所以从几何学上讲，它们都可能是罪魁祸首。但线索在这里开始中断了。我的意思是，它们都没有清晰的公开文档显示它们可以传输和干扰正确的频率。有些甚至几乎没有任何公开信息。

<details>
<summary>Original English</summary>

**Host**: The Algerian satellite wasn't the source. It was another victim. But what about the other 13? Any one of them could have been visible to all the stations at once. So geometrically, they could all be the culprit. But that's where the trail started to go cold. I mean, none of them had clear public documentation showing they could transmit and jam the right frequencies. And some of them had barely any public information at all.

</details>

**托德·汉弗莱斯**: 我们无法进一步缩小范围，因为我们对它们广播的信号、它们的强度、它们的模式等一无所知。所以，我们被困了大约四个月。

<details>
<summary>Original English</summary>

**Todd Humphreys**: We couldn't narrow it down further because of all of these things we didn't know about the signals they were broadcasting, how intense they were, what their pattern was. So, there we were stuck for about four months.

</details>

### 新的突破：原始无线电信号

**旁白**: 还有一个更根本的问题。他们迄今所做的一切都依赖于一个想法，即所有这些干扰事件都来自一颗单一卫星。

<details>
<summary>Original English</summary>

**Host**: And there was an even more fundamental problem. Everything they'd done so far relied on one idea, that all of these interference events were coming from a single satellite.

</details>

**托德·汉弗莱斯**: 这是一个非常有争议的假设。争议在于我和我的学生无法完全接受这个假设。如果我们打破这个假设，那就会减轻对**地球同步卫星**的关注。那么我们就可以将注意力转向许多其他卫星。但现在，我们名单上剩下的不是13颗，而是可能**100颗或更多卫星**。

<details>
<summary>Original English</summary>

**Todd Humphreys**: It was under a really controversial assumption. Controversial in that my student and I just couldn't come to fully embrace this assumption. If we broke our assumption, then that would relieve the focus on geostationary satellites. Then we could open up the focus on many other satellites. But now instead of 13 remaining on our list, it would expand to, you know, maybe 100 or more satellites.

</details>

**旁白**: 突然之间，他们不再是接近答案，而是感觉回到了原点。所以他们需要一种完全不同的方法。他们拥有的所有数据都来自**GNSS接收器**，这些接收器在内部处理一切。它们锁定卫星，跟踪信号强度，然后输出一个干净简化的测量值，即信号相对于背景噪声的强度。它们每秒只做一次。但这些干扰爆发只持续三到五秒，这意味着每个事件只在少数几个样本中被捕获。你可以看到信号下降了，但不能精确地知道它何时下降。没有足够的计时分辨率来比较一个接收器与另一个接收器，以查看哪个先受到冲击，或者干扰如何在网络中移动。他们需要的是原始的无线电信号本身。所以，他们开始设计专门的接收器，可以以更高的时间分辨率捕获数据。计划是在整个**欧洲**部署它们。但建造它们、安装它们以及等待新事件发生需要数月甚至数年。因此，2025年9月，他们在**巴尔的摩**的**导航学会会议**上公开了他们的调查。反响是立竿见影的。会议室挤满了人。每个人都想知道同一件事：这颗卫星是什么？谁是幕后黑手？

<details>
<summary>Original English</summary>

**Host**: And suddenly, instead of closing in on an answer, it felt like they were back at square one. So, they needed a completely different approach. All the data they had was from GNSS receivers that process everything internally. They lock onto satellites, track signal strength, and then output a clean simplified measurement, how strong that signal is compared to the background noise. And they do that just once per second. But these interference bursts only lasted three to five seconds, which means each event is captured in just a handful of samples. You can see that the signal dropped, but not precisely when it dropped. Not with enough timing resolution to compare one receiver to another, to see which one was hit first, or how the interference moved across the network. What they needed was the raw radio signal itself. So, they started designing specialized receivers that could capture the data in much higher temporal resolution. The plan was to deploy them all across Europe. But building them, installing them, and waiting for new events to happen would take months, maybe years. So, in September 2025, they took their investigation public at the Institute of Navigation Conference in Baltimore. And the response was immediate. The room was packed. Everyone wanted to know the same thing. What was this satellite and who was responsible?

</details>

**托德·汉弗莱斯**: 老实说，那是我参加过的最有趣的会议之一。我们几乎就像被召集起来进行一场大型集思广益会议，看看我们是否能作为一个社区解决这个问题，我和我的学生自己无法解决的问题。

<details>
<summary>Original English</summary>

**Todd Humphreys**: Honestly, it was one of the most fun meetings I've been part of. It was almost like we had been brought together for a big brainstorming session to see if we could crack this problem as a community that my student and I had not been able to crack by ourselves.

</details>

**旁白**: 神秘卫星的问题在研究界传播开来。**德国航空航天中心**提出了一个雄心勃勃的计划，即使用大型跟踪碟，对准候选卫星，并尝试实时捕获干扰。

<details>
<summary>Original English</summary>

**Host**: The question of a mystery satellite propagated throughout the research community. The German Aerospace Center came up with an ambitious plan to take a large tracking dish, point it at candidate satellites, and try to catch the interference in real time.

</details>

**托德·汉弗莱斯**: 但请记住，我们正在试图捕捉干草堆里的针，它只在短时间内出现，每月可能只发生一两次。

<details>
<summary>Original English</summary>

**Todd Humphreys**: But remember, we're trying to catch a needle in a haystack that only shows up over a short interval and only happens once, maybe once or twice a month.

</details>

**旁白**: 他们跟踪了一颗又一颗卫星，一无所获。没有信号，没有异常，没有突破。线索再次中断了。几周过去了，几个月过去了，直到一封电子邮件到来。

<details>
<summary>Original English</summary>

**Host**: They tracked satellite after satellite and nothing. No signal, no anomaly, no breakthrough. Yet again, the trail went cold. Weeks passed, then months, until an email arrived.

</details>

**托德·汉弗莱斯**: 我看了那封邮件，然后不得不重读，因为它几乎就像从我的梦中出现一样。你知道，这不可能是真的。他有来自两个不同站点的精美原始数据。

<details>
<summary>Original English</summary>

**Todd Humphreys**: I looked at the email and then I had to reread it because it was almost like it had come right out of my dreams. You know, this can't possibly be true. He had beautiful raw data from two different stations.

</details>

**旁白**: 终于，他们得到了他们一直缺少的东西，原始的无线电信号本身。来自两个站点——一个在**荷兰阿姆斯特丹**，一个在**挪威北部特隆赫姆**——的天线原始电压样本，以每秒数百万次的频率捕获实际的数字化无线电波。他们在2026年2月11日捕获了这些干扰事件。现在，他们不再问信号有多强，而是可以问：它何时到达？有了这些原始数据，他们分离出一个**2.3秒**的窗口，两个站点都记录了相同的事件。由于他们以**数十兆赫**的频率采样，他们可以对齐两个数据集，以精确定位干扰信号到达两个站点的确切时刻。这意味着他们可以测量信号到达每个站点的微小时间差。想象一下，信号到达**特隆赫姆**比到达**阿姆斯特丹**早大约**139微秒**。好吧，那告诉你，信号源必须比它离**阿姆斯特丹**更靠近**特隆赫姆**。这个限制给你一个形状，一个在空间中的曲线，即所有可能源位置的集合，在那里会观察到确切的时间差。在三维空间中，这变成了一种扭曲的表面，一个**双曲面**。任何传输信号的东西都必须位于那个表面上。由于原始数据具有令人难以置信的高分辨率，误差范围，即那个形状的厚度，延伸到太空数万公里，只有大约**五米**。

<details>
<summary>Original English</summary>

**Host**: At last, they had what they'd been missing, the raw radio signal itself. Samples of the raw voltage off the antenna capturing the actual digitized radio waves millions of times per second from two stations, one in Amsterdam in the Netherlands and one in Trondheim in Northern Norway. They captured these interference events on February 11th, 2026. And now, rather than asking how strong is the signal, they could ask, when did it arrive? With this raw data, they isolated a 2.3 second window where both stations recorded the same event. And because they were sampling at tens of megahertz, they could align the two data sets to pinpoint the exact moment the jamming signal arrived at both stations. This meant they could measure the tiny difference in when the signal reached each station. Imagine the signal reaches Trondheim roughly 139 microseconds before it reaches Amsterdam. Well, that tells you that the source must be slightly closer to Trondheim than it is to Amsterdam. And that constraint gives you a shape, a curve in space of all the possible locations of the source where that exact timing difference would be observed. In three dimensions, that becomes a kind of warped surface, a hyperboloid. Whatever transmitted the signal had to lie somewhere on that surface. And because the raw data was so incredibly high resolution, the margin of error, the thickness of that shape, stretching tens of thousands of kilometers into space, was only about five meters.

</details>

**托德·汉弗莱斯**: 因为我们非常在意避免错误，我们决定一周内互不交谈。我们将各自做自己的事情一周。然后我们会回来，比较笔记，希望我们没有犯相同的错误。我向扎克展示了我的发现，他向我展示了他的，结果并不相同。我不得不承认，因为我是教授，我非常坚持我的发现是正确的。但后来他指出了一些其他事情，他运行的其他检查。然后我意识到我的代码有错误。一旦我修复了那个错误，我最终得到了和他完全相同的时间差。

<details>
<summary>Original English</summary>

**Todd Humphreys**: And because we were so interested in avoiding errors, we just determined that we were not going to talk to each other for a week. We would do our separate thing for a week. And then we would come back together, compare notes, and we would hopefully have not made the same mistakes. And I presented my findings to Zach and he presented his to me and they were not the same. And I have to admit that because I'm the professor, I was pretty much insistent that my finding was correct. But then he pointed out a couple of other things, other checks that he'd run. And then I realized that I had an error in my code. And once I fixed that error, I ended up getting exactly the same time difference of arrival that he did.

</details>

### 锁定俄罗斯Cosmos 2546卫星

**旁白**: 现在他们有了一种方法来测试所有可能的卫星，而不仅仅是他们早期预测的14颗。对于每颗卫星，他们都采用其已知轨道，并询问如果信号来自这里，那么**阿姆斯特丹**和**特隆赫姆**之间会预期到什么时间差？然后他们将这个预测与真实数据进行比较。如果不匹配，那颗卫星就被排除了。由于他们有连续的**2.5秒记录**，他们可以更进一步。随着卫星的移动，那个**双曲面**会在空间中稍微移动。所以，真正的信号源必须始终与它对齐，这使得这个测试异常严格。

<details>
<summary>Original English</summary>

**Host**: And now they had a way to test every possible satellite, not just the 14 from their earlier predictions. For each satellite, they took its known orbit and asked if the signal came from here, what timing difference would we expect between Amsterdam and Trondheim? Then they compared that prediction to the real data. If it didn't match, the satellite was ruled out. And since they had a continuous two and a half second recording, they could take this a step further. As the satellite moved, that hyperboloid would shift slightly through space. So, the real source had to stay aligned with it the entire time, which made this test incredibly strict.

</details>

**托德·汉弗莱斯**: 只有一颗卫星与这个到达时间差测量值非常接近。事实上，它不仅仅是接近，而是完全吻合。

<details>
<summary>Original English</summary>

**Todd Humphreys**: And only one satellite was anywhere near this time difference of arrival measurement. And in fact, it wasn't just near, it was dead on.

</details>

**旁白**: 唯一可能的罪魁祸首是**俄罗斯卫星Cosmos 2546**。它完美地停留在**双曲面**上，与他们的数据在**200米**以内对齐，这完全在卫星公开可用轨道数据的不确定性范围内。值得一提的是，这项工作仍然是新的，尚未经过同行评审，但**欧洲**的独立团队已经验证了这些发现的某些方面。只有一个小问题。**Cosmos 2546**于2020年5月22日发射。所以，它无法解释追溯到2019年的事件。但后来他们发现**Cosmos 2546**是**六颗卫星**组成的星座的一部分。这个星座是**俄罗斯**早期导弹预警系统的一部分。

<details>
<summary>Original English</summary>

**Host**: The only possible culprit was a Russian satellite, Cosmos 2546. It remained perfectly on the hyperboloid, aligning with their data to within 200 meters, which is well within the uncertainty of the satellite's publicly available orbital data. Now it's worth saying here, this work is still new and it hasn't undergone peer review, but independent teams in Europe have verified aspects of these findings. There was only one slight issue. Cosmos 2546 was launched on the 22nd of May, 2020. So, it couldn't explain events going back to 2019. But then they discovered that Cosmos 2546 is part of a constellation of six satellites. This constellation is part of Russia's early missile warning system.

</details>

**托德·汉弗莱斯**: 它基本上是他们**金圆顶**的一部分。如果你听说过**美国金圆顶**，这是**俄罗斯导弹探测系统**的传感设备的一部分。

<details>
<summary>Original English</summary>

**Todd Humphreys**: It's basically part of their Golden Dome. If you've heard of the U.S. Golden Dome, this is part of the sensory apparatus for the Russian missile detection system.

</details>

**旁白**: 它们位于所谓的**莫尔尼亚轨道**。一条高度椭圆的路径，将它们带到**北半球**高空，在那里它们可以减速并停留。这是像**俄罗斯**这样的高纬度国家可以从多个卫星中获得**地球同步轨道**类似好处的方式。但这也意味着这个星座覆盖了全球大部分地区。因此，它们有能力在比我们所见范围更广的区域干扰**GNSS**，包括**美国**上空。这种模式已经告诉我们这不是随机的。频率告诉我们这不是自然的。现在我们知道它来自轨道上的军事系统。但意图，好吧，这更难证明。

<details>
<summary>Original English</summary>

**Host**: They sit in what's called a Molniya orbit. A highly elliptical path that carries them high over the Northern hemisphere, where they can slow down and linger. It's the way that high latitude countries like Russia can get the benefits of something like geostationary orbit across multiple satellites. But this also means this constellation covers large parts of the globe. So, they have the capability to jam GNSS across a far wider region than we've seen, including over the United States. The pattern already told us this wasn't random. The frequency told us it wasn't natural. And now we know it's coming from a military system in orbit. But intention, well, that's harder to prove.

</details>

**托德·汉弗莱斯**: 已经广播的信号非常强大。它比**GPS信号**本身强大数百倍。

<details>
<summary>Original English</summary>

**Todd Humphreys**: What is already being broadcast is enormously powerful. It's like hundreds of times more powerful than the GPS signals themselves.

</details>

### 干扰意图的猜测

**旁白**: 但它与**GPS频率**略有偏移，这看起来很奇怪。因为如果你想正确干扰**GPS**，你肯定会把干扰信号直接放在它上面。嗯，托德对此有一个理论。

<details>
<summary>Original English</summary>

**Host**: But it's slightly offset from the GPS frequency, which seems odd. Because surely if you want to jam GPS properly, you would put your jamming signal directly on top of it. Well, Todd actually has a theory about this.

</details>

**托德·汉弗莱斯**: 如果你要测试这种能力，那么你在你打算干扰的信号附近进行测试，但不是直接在那个信号上。你只进行短暂测试，以确保一切仍然正常。然后在未来的热冲突中，他们会调整他们的发射器到**GPS频段**。但现在它直接在那个频段上，破坏性会大得多。

<details>
<summary>Original English</summary>

**Todd Humphreys**: If you're going to test this capability, then you test it in the neighborhood of the signal you intend to jam, but not right on that signal. And you test it only briefly just to make sure everything's still working. And then in the eventual future, where there is a hot conflict, they go ahead and tune their transmitter down to the GPS band. But it's much more damaging now that it lies right on that band.

</details>

**德里克**: 所以，一种可能性是这样。我们所看到的是测试，一个系统正在被演练，而没有完全揭示它能做什么。虽然这目前只是一个理论，但还有另一个线索表明可能就是这种情况。原始数据还揭示了第二次干扰爆发，目标是较低的频率**1558.5兆赫**，这与**中国北斗导航系统**的信号重叠。

<details>
<summary>Original English</summary>

**Derek**: So, one possibility is this. What we've been seeing are tests, a system being exercised without fully revealing what it can do. And while just a theory at this point, there is another hint this might be the case. The raw data also revealed a second interference burst aimed at a lower frequency, 1558.5 megahertz, which overlaps with signals from the Chinese BeiDou navigation system.

</details>

**托德·汉弗莱斯**: 我会用最保守的方式说。我不能再自信地说这是意外了。我倾向于认为这是一种能力的周期性测试，如果它在愤怒中部署，将非常具有破坏性。

<details>
<summary>Original English</summary>

**Todd Humphreys**: I'll say it in the most conservative way possible. I can no longer say this is accidental with confidence. I'm leaning toward this being a periodic test of a capability that would be very damaging if it was deployed in anger.

</details>

**德里克**: 但是当我们与一个独立团队交谈时，他们也独立地将信号追溯到**俄罗斯导弹预警系统**的卫星，他们有另一个想法。

<details>
<summary>Original English</summary>

**Derek**: But when we spoke to a team that had independently traced the signals back to satellites in Russia's missile warning system, they had another idea.

</details>

**旁白**: 那么，持续测试某些东西会是非常奇怪的行为。所以，我们的另一种理论是，这些可能实际上是非常短、非常简短、非常具体的来自这些卫星的通信信息。

<details>
<summary>Original English</summary>

**Host**: So that'd be very odd behavior to be continually testing something. So, our alternative theory is that those might actually be very short, very brief, very specific comms messages coming from those satellites.

</details>

**德里克**: 如果这是真的，在这些频率上传输信息会提供一层保护，因为敌人不想干扰它们，并冒着干扰自己导航系统的风险。

<details>
<summary>Original English</summary>

**Derek**: And if that were true, transmitting messages on these frequencies would provide a layer of protection because the enemy wouldn't want to jam them and risk disrupting their own navigation systems.

</details>

**旁白**: 我不是说它不是干扰。这仍然是一个非常有力的可能性。我认为关键是，这有一些奇怪的地方，并且这里显然有一个替代解释。

<details>
<summary>Original English</summary>

**Host**: I'm not saying it's not the jamming. That's still a very strong possibility. I think the point is there are some odd things about that and there is clearly here an alternative explanation.

</details>

### 潜在的巨大影响与解决方案

**旁白**: 但无论这些信号是秘密信息还是天基干扰系统的测试，事件本身都非常短暂。这或许能解释另一件事。为什么多年来都没有引起注意。但如果这个系统全面启用，影响可能是巨大的。当我们今天看到大规模**GPS干扰**的地图时，你几乎完全看到的是商业飞机受到地面干扰器影响的报告。典型的客机巡航高度在**30000到42000英尺**之间，这足以在大范围内保持对干扰信号的直接视线。但在地面，建筑物和地形会屏蔽我们大部分基础设施免受干扰。

<details>
<summary>Original English</summary>

**Host**: But whether these signals were covert messages or tests of a space-based jamming system, the events themselves were incredibly brief. And that might explain something else. Why this went unnoticed for years. But if this system were ever fully switched on, the impact could be enormous. When we see maps of massive GPS interference today, you are almost entirely looking at reports from commercial aircraft affected by ground-based jammers. Typical airliners cruise at altitudes between 30,000 and 42,000 feet, which is high enough to remain in direct line of sight of jamming signals across vast distances. But at ground level, buildings and terrain shield much of our infrastructure from that interference.

</details>

**托德·汉弗莱斯**: 但太空中的一切都是视线可见的，是的。它是一种看不见的公用事业，支持着几乎所有的技术。它对我们每天的生活方式至关重要。**美国**将**GPS**作为送给世界的一份礼物。聪明的工程师们利用这个免费且运行良好、非常精确的东西，并将其融入到各种系统中。这是一个棘手的问题。你真的不知道所有的依赖关系是什么，所有的相互连接在哪里，因为它已经遍布全球。

<details>
<summary>Original English</summary>

**Todd Humphreys**: But everything is line of sight from space, yeah. It's an invisible utility that supports virtually every technology. And it's essential to the way we live every day. The United States made GPS its gift to the world. And clever engineers took this free thing that works really well and very precisely and incorporated it into all kinds of systems. It's one of those wicked problems. You really don't know what all the dependencies are and where all the interconnections are because it's just proliferated throughout the world.

</details>

**德里克**: 全球卫星导航系统支撑着航空和全球航运。它同步金融系统，保持蜂窝塔时间准确。它对物流网络、网约车应用程序、配送系统，甚至是约会应用程序都至关重要。这些系统在如此广阔的区域内中断，就像这些卫星所能做到的那样，可能会影响数亿人。

<details>
<summary>Original English</summary>

**Derek**: Global satellite navigation systems underpin aviation and global shipping. It synchronizes financial systems, keeps cell towers on time. It is crucial for logistics networks, ride hailing apps, delivery systems, even dating apps. A disruption of these systems across an area as large as what these satellites are capable of could affect hundreds of millions of people.

</details>

**托德·汉弗莱斯**: 这将在全世界引发恐惧的冲击波，不仅仅是在**欧洲**，因为一种全新的天基武器将被揭示。人们会知道，在他们选择的任何时候，**俄罗斯**都可以在他们的国家或他们的大陆上部署这种武器。我确实认为这是目前正在进行的电子战背景冲突的巨大升级。

<details>
<summary>Original English</summary>

**Todd Humphreys**: It would send shockwaves of fear through the world, not just through Europe, because an entirely new weapon from space would have been revealed. And people would know that at any time of their choosing, Russia could deploy this over their country or over their continent. I do think that this is a massive escalation in the electronic warfare background conflict that's going on right now.

</details>

**德里克**: 现在，这听起来很吓人，但事实是我们早就应该担心这个脆弱的系统了。

<details>
<summary>Original English</summary>

**Derek**: Now, this sounds scary, but the truth is we should have been worried about this fragile system already.

</details>

**托德·汉弗莱斯**: 威胁一直存在。严重的**太阳事件**可能使大气层电离，阻止各种来自太空的信号进入，或者它可能摧毁卫星。我们可能会在中地球轨道上看到**凯斯勒效应**的版本，卫星被碎片摧毁。所以，每个人都应该已经感到担忧。他们应该继续担忧。这只是另一个例子。

<details>
<summary>Original English</summary>

**Todd Humphreys**: The threat has always been there. Severe solar events could ionize the atmosphere and keep all kinds of signals from space from coming in, or it could destroy satellites. We could have a version of the Kessler effect in medium Earth orbit, and satellites be destroyed by debris. So, everybody should have already been concerned. They should continue to be concerned. And this is just another example of why.

</details>

**德里克**: 但好消息是，我们已经确切地知道如何解决这个问题。它涉及建立一个不完全依赖微弱卫星信号的未来系统。

<details>
<summary>Original English</summary>

**Derek**: But the good news is, we already know exactly how to fix the problem. It involves building a future system that doesn't rely entirely on weak satellite signals.

</details>

**托德·汉弗莱斯**: 我们建议一个有韧性的国家**PNT架构**将包括来自太空的信号、地面广播和光纤，因为这三者在物理现象上完全不同，影响其中一个不会影响另外两个。

<details>
<summary>Original English</summary>

**Todd Humphreys**: We suggest that a resilient national PNT architecture would be signals from space, terrestrial broadcast, and fiber, because those are three completely different phenomenologies in a vector that would impact one, would not impact the other two.

</details>

**旁白**: 一些国家已经这样做了。**韩国**、**中国**和**英国**等国家正在建设不依赖太空信号的备用网络。他们使用**光纤电缆**安全地共享地球上的**原子钟**时间。对于导航，他们转向**eLoran**等系统，这是一种更难被压制的大功率无线电塔。其他解决方案甚至正在开发中，使用磁性和量子系统，利用地球磁场的微小变化来确定位置。所以，你不需要任何外部信号。但尽管如此，大多数国家，包括**美国**，仍然高度依赖**GPS**和其他卫星导航系统。在这个视频中，我们一直在讨论干扰，但还有另一种**GNSS干扰**，它将你的真实信号替换为虚假信号，悄悄地给你一个看起来完全真实的定位。所以，如果你信任它，它可以把你引导到完全不同的地方。这被称为**GPS欺骗**。它每天影响超过**1500架航班**。在海上，我们也看到了同样的情况。船只跳跃到难以置信的距离，短暂消失或重新出现在不可能的位置，甚至在陆地上。这是一种系统的、地理上集中的现实扭曲，无论是空中还是海上。如果你想了解更多，请在评论中告诉我们。这个故事基于**德克萨斯大学奥斯汀分校**的**托德·汉弗莱斯教授**和他的学生**扎克·克莱门茨**的研究。他们的工作链接在描述中。我要感谢他们所有的帮助，以及与我们分享他们的发现。当然，我也要感谢你的观看。

<details>
<summary>Original English</summary>

**Host**: Some countries are already doing this. Places like South Korea, China, and the UK are building out backup networks that don't rely on signals from space. They're using fiber optic cables to securely share time from atomic clocks here on Earth. And for navigation, they're turning to systems like eLoran, huge high-powered radio towers that are much harder to overwhelm. Other solutions are even being developed using magnetic and quantum systems that use subtle variations in the Earth's magnetic field to work out position. So, you don't need any external signals. But despite all of this, most countries, including the United States, still remain highly dependent on GPS and other satellite navigation systems. In this video, we've been talking about jamming, but there's another kind of GNSS interference, one that swaps your real signal for a fake one, quietly feeding you a location that looks completely real. So, if you trust it, it can guide you somewhere else entirely. This is known as GPS spoofing. It's affecting over 1,500 flights per day. And at sea, we're seeing the same thing. Ships are jumping implausible distances, briefly disappearing or reappearing in impossible locations, even on land. It's a systematic, geographically clustered distortion of reality, both in the air and at sea. If you wanna know more about that, let us know in the comments. This story was based on research by Professor Todd Humphreys and his student, Zach Clements, at the University of Texas at Austin. There's a link to their work down in the description. I wanna thank them for all their help and for sharing their findings with us. And of course, I wanna thank you for watching.

</details>