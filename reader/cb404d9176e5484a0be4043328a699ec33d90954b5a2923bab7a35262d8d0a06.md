---
author: All-In Podcast
date: '2026-07-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TqNiSTeNtb0
speaker: All-In Podcast
tags:
  - robotics-form-factor
  - industrial-inspection
  - humanoid-vs-quadruped
  - sensor-technology
  - automation-operations
title: 人工智能在现实世界中的应用与机器人技术探讨
summary: 文章围绕一个名为 Machina 的会议展开，重点讨论了人工智能在工业巡检、移动机器人形态（如四足机器人与人形机器人）以及商业价值方面的应用。内容涵盖广告平台模式的成功案例和先进传感器的超人类感知能力，并展望了未来机器人的职业发展路径。
insight: ''
draft: true
series: ''
category: deployment
area: tech-engineering
project: []
people: []
companies_orgs:
  - AppLovin
  - Anybotics
  - Boston Dynamics
  - Agility Robotics
products_models:
  - ANYmal
  - Spot robot
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

### Machina 大会开场与赞助商播报

**Jay Cal**: 大家好，我是你们的老朋友 Jay Cal。我现在在法国巴黎，参加一个名为 Machina 的会议。这个会议的主题基本上是探讨人工智能在现实世界中的应用。请原谅我的机器人。感谢大家的收听，我们现在就开始。我要全情投入了。

<details>
<summary>Original English</summary>

**Jay Cal**: Hey everybody, it's your boy Jay Cal. I'm here in Paris, France at a conference called Machina. It's basically AI in the real world. Pardon my robot. Thanks for tuning in and let's get started. I'm going all in.

</details>

**Narrator**: AppLovin 从一个价值 8 美元的域名起步，在没有风险投资的情况下，成为了全球最大的广告平台之一。现在，同样的引擎正在为电子商务提供 AppLovin 广告服务。您的广告将在移动游戏中运行，触达超过十亿人，并获得全屏、无干扰的注意力。该平台能自动寻找买家并优化利润。您只需设定目标，剩下的交给它。一个厨具品牌从 400 万美元增长到了 1600 万美元，实现了盈利，并且今年的目标是有望达到 8000 万美元。立即访问 applovin.com/allin，启动您的第一个广告活动。

<details>
<summary>Original English</summary>

**Narrator**: AppLovin started with an $8 domain and no VC funding and became one of the largest ad platforms in the world. Now that same engine powers AppLovin ads for e-commerce. Your ads run inside mobile games reaching over a billion people with full screen distraction-free attention. The platform finds buyers and optimizes for profit. You set the target, it does the rest. One cookware brand went from $4 million to $16 million, turned profitable, and is on pace for 80 million this year. Visit applovin.com/allin to launch your first campaign today.

</details>

### 对话 Anybotics CEO：聚焦工业巡检

**Jay Cal**: 好了，各位。我们在巴黎继续对当今顶级机器人公司进行采访。非常高兴能邀请到 Peter Funkhouser 博士来到我们的节目。你是 Anybotics 的联合创始人兼首席执行官。你们制造了 ANYmal。听懂了吗？你们中很多人都喜欢玩双关语。但你在这个领域已经工作了将近 20 年。这家公司也成立 10 年了。前五年更像是一个研究实验室。过去五年，你们怎么称呼这种基于狗的机器人？

<details>
<summary>Original English</summary>

**Jay Cal**: All right, everybody. Our interviews with the number one companies in robotics today continue here in Paris. Really excited to have Dr. Peter Funkhouser on the program. You're the co-founder and CEO of Anybotics. You make the ANYmal. Get it? A lot of you have puns. But you've been working in this space for close to 20 years. The company's been around for 10. First five years kind of a research lab. Last 5 years your what do you call these dog based robots?

</details>

**Dr. Peter Funkhouser**: 嗯，这是一个巡检解决方案，对吧？它主要是为了在关键基础设施中进行数据收集和理解。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Well, it's an inspection solution, right? It's about data collection and understanding in critical infrastructure.

</details>

**Jay Cal**: 但它的外形是一个四足机器人，或者说是一只狗，正如你……

<details>
<summary>Original English</summary>

**Jay Cal**: But the form factor is a four-legged robot or a dog as you...

</details>

**Dr. Peter Funkhouser**: 我们喜欢称它为机器狗（dogbot），但是……

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: We like to call it a dogbot, but...

</details>

**Jay Cal**: 为什么这种狗的形态成为了标准？你不是唯一一个制造它的人。现在有很多人在做这个。为什么这一个是第一个达到相对规模并投入部署的？

<details>
<summary>Original English</summary>

**Jay Cal**: Why did that dog format become the standard? You're not the only person making it. There's many people making it now. Why did that one become the first one to hit, you know, relative scale and for a deployment?

</details>

**Dr. Peter Funkhouser**: 是的，在大自然中，你知道，很多动物都有四条腿，所以这是有原因的。因此，毫无疑问，它具有极佳的机动性。你可以爬楼梯。它可以去任何人类能去的地方。所以，它兼具灵活性和平衡性。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Yeah, in nature, you know, a lot of animals have four legs, so there's a reason to that. So, for sure, you have a great mobility. You can climb stairs. You can go anywhere a person can go. So dexterity and balance.

</details>

**Jay Cal**: 机动性，对吧？

<details>
<summary>Original English</summary>

**Jay Cal**: Mobility, right?

</details>

**Dr. Peter Funkhouser**: 平衡性，还有稳定性。四条腿为你提供了很宽的占地面积和很多立足点，因为我们在恶劣的环境中工作，比如湿滑的地板、下雨、下雪以及长满草的地方。所以四条腿是一个非常好的形态。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Balance, but also stability. Four legs give you a wide footprint, a lot of footholds to hold on to because we work in nasty environments, slippery floors, rain, snow falling down, grass growing. So four legs is a real good format.

</details>

### 半人马形态 vs 双足人形机器人

**Jay Cal**: 好吧，这可能是一个愚蠢的问题，但为什么我们不为人类版本制造半人马形态呢？当人们在制造波士顿动力的 Optimus、Neo、Atlas 这些双足站立机器人时，主要的担忧是它们总是会摔倒。它们在演示中经常摔倒，如果摔倒了，可能会弄断某人的脚踝。为什么不给它们装上四条腿呢？

<details>
<summary>Original English</summary>

**Jay Cal**: Well, now this is a silly question, but why don't we make centaurs for the human versions when people are making the Optimus, the Neo, the Atlas from Boston Dynamics, those standup robots with two legs. The concern is they're always going to fall over. They constantly fall over in demos and if they fall over, they're going to break somebody's ankle. Why not put four legs on those?

</details>

**Dr. Peter Funkhouser**: 你当然可以这么做。这真的取决于用例。如果你需要在咖啡店工作，把它带到狭窄的空间里，对吧？你希望在视线水平进行工作。也许人形机器人更好。但在我们所服务的追求腿部稳定性的设施中，有足够的空间可以四处走动。是的，这就是完美的形态。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: You could absolutely. And it really depends on the use case. If you need to work in a coffee shop, bring it to narrower spaces, right? You want to work in eye level. Maybe a humanoid is better. In the facility that we work for leg stability, there's enough space to go around. Yeah. It's the perfect format.

</details>

**Jay Cal**: 我不信。我认为所有的咖啡馆都应该配备半人马。就像希腊神话里的那样。

<details>
<summary>Original English</summary>

**Jay Cal**: I don't buy it. I think all the cafes should have centaurs in Greek mythology.

</details>

**Dr. Peter Funkhouser**: 就是半人马。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: It's a centaur.

</details>

**Jay Cal**: 我觉得那应该成为新标准。你们找到了一个非常有效的首选应用场景，那就是检查极其重要的基础设施，而且过去五年里，你们已经部署了成百上千台这样的机器人。

<details>
<summary>Original English</summary>

**Jay Cal**: I think that should be the new standard. You found a really effective first use case which is inspecting really important infrastructure and now you have thousands of these... hundreds of these deployed over the last five years.

</details>

**Dr. Peter Funkhouser**: 是的。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Yeah.

</details>

### 超越人类的传感器与商业价值

**Jay Cal**: 这些设备非常昂贵。购买它们需要大几十万美元。

<details>
<summary>Original English</summary>

**Jay Cal**: These are expensive. They're low hundreds of thousands of dollars to buy them.

</details>

**Dr. Peter Funkhouser**: 是的。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Yeah.

</details>

**Jay Cal**: 而且要运营它们，我猜每年的服务合同也需要几万美元。

<details>
<summary>Original English</summary>

**Jay Cal**: And to operate them, I'm assuming tens of thousands a year in service contracts.

</details>

**Dr. Peter Funkhouser**: 所以，它们不是家用的。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: So, they're not for home use.

</details>

**Jay Cal**: 这些是工业级的，上面装有很多传感器。所以，如果你要去检查一条含有天然气的管道。

<details>
<summary>Original English</summary>

**Jay Cal**: These are industrial and they have a lot of sensors on them. So, if you were going to inspect a pipeline with natural gas in it.

</details>

**Dr. Peter Funkhouser**: 没错。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Right.

</details>

**Jay Cal**: 这些东西可以在任何天气下外出，并且它们能感知到管道上人类无法感知的事物。对吧？

<details>
<summary>Original English</summary>

**Jay Cal**: These things can go out in any weather and they can sense things on that pipeline that a human can't. Correct?

</details>

**Dr. Peter Funkhouser**: 是的，没错。对我们来说，这不是关于取代劳动力，对吧？而是我们能做得更好些什么？我们能做哪些超越人类的事情？巡检就是一个很好的例子。我们的眼睛和耳朵无法感知所有的信号。微量的气体泄漏，设备过热等，通过机器人上的摄像头、热像仪、声学麦克风、气体浓度传感器以及所有这些设备。我们在里面塞满了传感器和人工智能，你可以做到远超人类所能做到的事情。因此，其经济效益在于避免停机时间。这些资产，如果它们停止运转，每小时会损失数十万的收入。所以我们能为他们节省的每一分钟、每一小时，本质上就足够支付这些机器人的费用了。这就是为什么我们能在机器人上配备极其昂贵的传感器和极其昂贵的 GPU。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Yeah, that's right. For us, it's not about labor replacement, right? It's what can we do better? What can we do superhuman? Inspection is a great example. Our eyes and ears don't perceive all the signals. Micro gas leakages, temperature equipment overheating with the cameras on the robot, thermal cameras, acoustic microphones, gas concentrations and all of that. We pack it full of sensors and AI and you can go way beyond what a human can do. So, the monetary benefit is avoiding downtime. These assets, if they stop, they lose revenues in hundreds of thousands per hour. So every minute, every hour we can save them essentially pays for the robots. So that's why we can afford having really expensive sensors, really expensive GPUs on top of a robot.

</details>

**Jay Cal**: 是的，这些设备上搭载了极其强大的计算能力，对吧？

<details>
<summary>Original English</summary>

**Jay Cal**: Yeah, these have seriously powerful compute on them, right?

</details>

**Dr. Peter Funkhouser**: 对。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Right.

</details>

### 续航、自动化与边缘计算

**Jay Cal**: 那么它们必定配备了相当大容量的电池。所以这些设备能执行多久的任务？一两个小时？

<details>
<summary>Original English</summary>

**Jay Cal**: And they have to have a significant amount of battery power then. So these things can do a mission of what? An hour or two?

</details>

**Dr. Peter Funkhouser**: 两个小时。然后回到扩展坞充电一个小时。但它们会一遍又一遍地做这件事。我们的一些客户每天运行这些任务多达 40 次。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Two hours. An hour docking station to come back charge. But they do this over and over. Some of our customers run these missions 40 times a day.

</details>

**Jay Cal**: 14 次，5 次，4 次……因为他们关心的是电弧炉升温时的某一个特定时间点。他们想知道那一分钟内正在发生什么。

<details>
<summary>Original English</summary>

**Jay Cal**: 14, 5, 4... because they're interested in a specific point when the electric arc furnace goes up. They want to know in that minute what's happening.

</details>

**Dr. Peter Funkhouser**: 派人进去太危险了。热像仪也会被烧毁。他们就在那个时刻需要一个机器人。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Too dangerous to send in a person. Thermal cameras burn. They need a robot right at that moment.

</details>

**Jay Cal**: 明白了。而且它们必须充电，而不是热插拔电池。

<details>
<summary>Original English</summary>

**Jay Cal**: Got it. And they have to charge not hot swapping the batteries.

</details>

**Dr. Peter Funkhouser**: 不，你需要的是免提的自主性。甚至没有人应该被这里有个机器人而打扰。他们不在乎机器人。实际上，他们甚至不想要机器人。他们想要的是数据。他们想要的是洞察力。机器人只是一个手段，为了精确收集数据的目的。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: No, you want hands-free autonomy. Nobody should even be bothered that there's a robot. They don't care about the robot. Actually, they don't even want the robot. They want the data. They want the insights. The robot is a means to an end to collect the data precisely.

</details>

**Jay Cal**: 到什么程度你才能卸下非常耗电的计算任务，把它放到云端进行？

<details>
<summary>Original English</summary>

**Jay Cal**: At what point can you offload the very power hungry compute and put it in the cloud?

</details>

**Dr. Peter Funkhouser**: 我们也会那样做。总是有两个部分。有一部分需要在这个机器人上实时运行，因为你也无法保证网络连接、避障、数据质量，你得确保拿到了正确的数据。如果你把一张模糊的图片上传到云端，那就太晚了。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: We also do that. There's always two parts. There's parts that need to run real time on the robot because you also cannot guarantee connectivity, obstacle avoidance, data quality, making sure you have the right thing. If you upload a blurry image to the cloud, it's too late.

</details>

**Jay Cal**: 但是在云端，你们当然会进行上下文分析、历史停机时间分析等等。

<details>
<summary>Original English</summary>

**Jay Cal**: But in the cloud, of course, you do contextual analysis, historic downtime analysis, etc.

</details>

**Dr. Peter Funkhouser**: 有人要求这些设备能够连续运行 24 小时或 12 小时吗？没有，绝对没有。所以最长也就是在 8 小时左右的范围内。这样它才有足够的时间充电。如果你需要超过这个时间，那是很少见的。更频繁地执行任务会带来边际收益递减。但你必须进行管理。他们现在是人工去做的，也许一天一次或两次。而现在他们可以获得 8 次、15 次、20 次的频率，对吧？所以它的频率已经大幅度提升了。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Are people asking for these to be able to operate for 24 hours yet or 12 hours? No, for sure. So the maximum is in the 8 hour range. So it has enough time for charging. If you need to go beyond that, that's rare. There's diminishing returns to more frequently do it. But you have to manage. They do it manually today, maybe once or twice a day. And they get 8, 15, 20 times now, right? So it's already the frequency goes massively up.

</details>

**Jay Cal**: 是的。

<details>
<summary>Original English</summary>

**Jay Cal**: Yeah.

</details>

**Dr. Peter Funkhouser**: 不仅没有把人置于险境，而且质量也高得多。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Without putting people into harm's way, plus the quality is so much higher.

</details>

### 海上作业与极端环境的科幻级应用

**Jay Cal**: 目前你们用这些设备所进行的最令人着迷的科幻级部署是什么？

<details>
<summary>Original English</summary>

**Jay Cal**: What's the most fascinating science fiction deployment you have currently with these?

</details>

**Dr. Peter Funkhouser**: 是啊。我的意思是，真正令人兴奋的是任何海上的作业，对吧？人们乘坐直升机飞出去。每一次直升机飞行的成本都在数万美元。所以，如果你在海上，情况非常棘手，对吧？它需要正常工作。周围几乎没有人。它需要……

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Yeah. I mean, what's really exciting anything offshore, right? People fly out with helicopters. Every helicopter flight costs in the tens of thousands. So, but if you're offshore, it's very tricky, right? It needs to work. There's almost no people around. It needs to be...

</details>

**Jay Cal**: 这些是石油钻井平台。

<details>
<summary>Original English</summary>

**Jay Cal**: These are oil rigs.

</details>

**Dr. Peter Funkhouser**: 海上石油和风能也是。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Oil and wind energy offshore as well.

</details>

**Jay Cal**: 啊，是的。但等一下。这些东西不在水里运作。那么，它们是如何与海洋里的风车配合工作的呢？

<details>
<summary>Original English</summary>

**Jay Cal**: Ah, yes. But wait a second. These things don't operate in the water. So, how do they work with windmills in the ocean?

</details>

**Dr. Peter Funkhouser**: 周围有成百上千个风车。它们汇集到一个变电站。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: There's windmills around hundreds of them. They come together to a transformer station.

</details>

**Jay Cal**: 哦，在传输之前，那里把交流电转换为直流电……而那通常是一个有人值守的设施，一个大型转换器。这就是机器人工作的地方。

<details>
<summary>Original English</summary>

**Jay Cal**: Ah that transforms to AC to DC before it trans and that's a manned facility typically a big converter. This is where the robot operates.

</details>

**Jay Cal**: 明白了。它们能在南极洲之类这种恶劣条件下工作吗？你们已经在那里部署过它们了吗？

<details>
<summary>Original English</summary>

**Jay Cal**: Got it. Can they operate like in severe conditions like the Antarctic and stuff like that and have you deployed them there yet?

</details>

**Dr. Peter Funkhouser**: 在挪威肯定是有的。也就是在零下 20 度的环境，而在沙漠里则高达 40、50、60 度。对。所以，这正是你想派机器人进去的地点。温度、灰尘、湿度，但最重要的是，我们现在有一个机器人可以进入爆炸性环境，你知道，在石油天然气和化工领域，空气中会含有甲烷。你是绝不能产生火花的。因此，我们制造了一种特殊的机器人，保证不会产生火花。在这类人们不愿意涉足，但对机器来说却是完美用例的危险环境中。这就是我们要把机器人派进去的地方。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Well in Norway for sure. So that's - 20° in deserts plus 40 50 60°. Right. So that's exactly the point where you want to send in a robot. temperatures, dust, humidity, but most importantly, we have a robot now that goes into explosive atmospheres where there's, you know, in oil and gas and chemicals, methane in the air. You're not allowed to, you know, create a spark. So, we built a special robot that's guaranteed not to create a spark. This is where you don't want to have people, but for a machine, that's a perfect case, right? Dangerous environment. This is where we're sending robots in.

</details>

**Jay Cal**: 那真是太迷人了。所以，如果你在二叠纪盆地（Permian basin）并且有东西泄漏，这是最危险的，这些石油钻井平台和天然气泄漏。这可是真正会出人命的地方。

<details>
<summary>Original English</summary>

**Jay Cal**: That's fascinating. So if you're in the Peran basin and something's leaking, that is one of the most dangerous these oil rigs and gas leaks. This is where people seriously die.

</details>

**Dr. Peter Funkhouser**: 是的。而且你想知道它什么时候发生，但又不想引发事故。所以这就是一个完美的用例。

<details>
<summary>Original English</summary>

**Dr. Peter Funkhouser**: Yes. And you don't want you want to know when it's happening, but you don't want to create a problem. So that's a perfect case.

</details>

<!-- chunk 2/9 -->

### 水下机器人与维护操作的未来

**Speaker A**: 我是说，我还是要继续用科幻的思路来想，但把这些东西扔到海底似乎在未来某个时刻是个理所当然的事情。

<details>
<summary>Original English</summary>

**Speaker A**: I mean, I'm going to keep going sci-fi, but dropping these things into the bottom of the ocean seems like a no-brainer at some point.

</details>

**Speaker B**: 嗯，现在有潜水艇，对吧？我们目前还没做那个，但我同意你的看法。机器人就应该在人们不该去的地方工作：危险、偏远的地点，对吧？以及执行枯燥、重复的任务。这就是我们……

<details>
<summary>Original English</summary>

**Speaker B**: Well, there's submarines, right? We don't do that right now, but I agree, right? Robots should work in environments where people shouldn't be dangerous, remotes, right? boring repetitive task. This is what we...

</details>

**Speaker A**: 目前那是另一种产品形态。但是，现在已经有人在水面以及水下浅层进行创新了，对吧，这些机器人实际上不是在做检查，而是在监控系统，显然是为了军事目的。嗯，如果你在外面进行检查，发现有气体泄漏，而派人类去那里又很危险，那你打算什么时候在这些机器人上装一些设备，让你在外面的时候能把那该死的泄漏给修好？这肯定是你们的终极目标，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: That's a different form factor right now. But there are people creating on the surface and then slightly under the surface, right, robots that are doing essentially not inspections but monitoring systems for obviously the military. Um well, if you're out there inspecting and there's a gas leak and it's dangerous to send humans out there, when are you going to put some equipment on these to fix the goddamn leak while you're out there? And that must be the holy grail, is it not?

</details>

**Speaker B**: 是的。一旦你能检测到问题，客户就会问：“你能解决它吗？你能修好它吗？你能转动阀门吗？”今天还不行。你知道，在演示中可以。但在现实中，要在爆炸性环境中达到 99.9% 的可靠性，这仍处于开发阶段。第一步是合上控制杆、打开控制柜。最终你会希望通过人工操作，也许使用三四条机械臂来修理机器，对吧。那仍然……你知道，AI 会在那里帮助我们，但我们还有很多工作要做。所以你看到的很多类人机器人叠衣服的演示，那是一个非常受控的环境。一旦你到了室外，遇到冰雹风暴，对吧，还有冰冻的温度，无论是环境还是感知都不一样了，但最终我们预见未来这个问题会被解决。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Once you can detect a problem, customer ask, can you solve it? Can you fix it? Can you turn? Not today. You know, in a demo, yes. But in reality getting to 99.9% reliability in explosive atmosphere that's still in development first step is closed levers open cabinets eventually you want to have by manual manipulation maybe three four arms to fix the machine right that's still you know AI will help us there still a lot of work ahead of us so a lot of the demos you see of humanoids folding laundry that's a very controlled environment once you're outdoor in a hail storm right um freezing temperatures it's different also for perception but eventually we foresee the future that this will be solved

</details>

### 供应链与应对中国机器人的竞争

**Speaker A**: 你的机器人有多大比例是从中国采购的？

<details>
<summary>Original English</summary>

**Speaker A**: What percentage of Your robot is sourced from China.

</details>

**Speaker B**: 零。

<details>
<summary>Original English</summary>

**Speaker B**: Zero.

</details>

**Speaker A**: 0%？

<details>
<summary>Original English</summary>

**Speaker A**: 0%.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 那是因为在欧盟和挪威这是被禁止的，还是说这是你们自己的选择？

<details>
<summary>Original English</summary>

**Speaker A**: And is that because in the EU and Norway it's banned or that's a choice?

</details>

**Speaker B**: 这只是历史原因造成的，我们进行本地采购，然后你会从美国等地获取芯片。而且对我们的一些客户来说这很重要。另外，因为我们是 10 年前起步的，所以很多东西都是我们自己制造的。如今对于很多架构，你可以在全球各地买到更便宜的零部件。所以，关键在于要聪明地选择从哪里采购零部件，哪些是核心的有源器件，哪些只是金属结构件。嗯，所以要想驾驭这个世界确实很难，但利用某些硬件的商品化趋势，对我们来说在成本上是有意义的。

<details>
<summary>Original English</summary>

**Speaker B**: That happened just historically that we source locally and you get chips from the US etc. And for some of our customers it's important and we built a lot ourselves right because we started 10 years ago. So a lot of the architecture nowadays you get cheaper components around the globe. So it's about being smart where you get components from, which one are active, which one are just metals. Um, so for sure it's a hard world to navigate, but tapping into the commoditization of certain hardware that makes sense for us costwise.

</details>

**Speaker A**: 现在中国以外，还有谁在这方面比较专业？是越南、印度、台湾吗？比如你从哪里可以采购到执行器以及很多这类零件？

<details>
<summary>Original English</summary>

**Speaker A**: Who's specializing in that outside of China now? Is it Vietnam, India, Taiwan? Where can you source like the actuators and and a lot of this

</details>

**Speaker B**: 毫无疑问，中国在推动这方面是排第一的。欧洲也有很好的公司，对吧？美国也是。所以可以肯定是这三个地区。如果只是关于人工组装，你也可以去其他地方，但你要获取的是核心专业技术，要找的是制造那个零部件的人。

<details>
<summary>Original English</summary>

**Speaker B**: for sure? China is number one pushing. There's good companies in Europe, right? In the US as well. So these three regions for sure if it's just about labor assembly you can go elsewhere as well but you want to get the core expertise somebody who builds that component.

</details>

**Speaker A**: 明白了。那你现在怎么看中国？他们一直在窃取知识产权。我猜他们已经窃取了你们的。而且毫无疑问，其他人的知识产权正在中国被大规模窃取。他们正在制造价格便宜 80% 的机器人，并准备尝试将它们部署给你们同样的客户群。我很确信这一点。你是如何看待中国机器人带来的威胁的？

<details>
<summary>Original English</summary>

**Speaker A**: Got it. And how do you look at China now? They've been stealing the IP. I'm assuming they've stolen yours already. Um and certainly other people's IP is being stolen at scale in China and they're building robots that are going to be 80% cheaper and they're going to try to deploy them to the same customer base. I am certain. How are you thinking about the threat of Chinese robotics?

</details>

**Speaker B**: 如果你看看今天来自中国的机器人，那台设备是一件走起路来非常漂亮的硬件。非常棒的工程设计，我非常喜欢。它们还能做后空翻。是的。但他们并没有解决根本问题。我们的客户不会拿一个单一平台与我们所拥有的完整解决方案去比较。你需要自主性、检查功能、智能、工作流集成，还有很多其他东西，对吧？他们只是在硬件上有差异。

<details>
<summary>Original English</summary>

**Speaker B**: If you look at the robot from China today, that device is a piece of hardware that can walk beautifully. Great engineering. Love it. Do back flips. Yeah. But they're not solving the problem. Our customers don't compare a platform to the full solution that we have. Do you need autonomy, inspection, intelligence, the workflow integration, so much more, right? It's just a hardware difference.

</details>

**Speaker A**: 所以像线束、外壳以及周边的服务，他们都没有提供。

<details>
<summary>Original English</summary>

**Speaker A**: So the harness, the wrapper, the services around it, they're not providing that.

</details>

**Speaker B**: 然后还有对数据的信任问题，对吧？我们处理的是非常敏感的数据。我们在网络安全等所有这些领域都拥有 ISO 认证，对吧？所以我们是这样参与竞争的。

<details>
<summary>Original English</summary>

**Speaker B**: And then the trust in the data, right? We call very sensitive data. We have ISO certification for cyber security, all these topics, right? So that's how we compete.

</details>

**Speaker A**: 所以你可能不想把核电站的最新数据发送给中国共产党。你的意思是……

<details>
<summary>Original English</summary>

**Speaker A**: So you might not want to send the nuclear power plants latest uh data to the Chinese Communist Party. You're saying

</details>

**Speaker B**: 你肯定不希望你的关键基础设施里有 15 个摄像头，而且还是由别人控制的。

<details>
<summary>Original English</summary>

**Speaker B**: you don't want to have 15 cameras in your critical infrastructure that somebody else controls.

</details>

**Speaker A**: 是的，我有点开玩笑了，但是……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I'm being a bit facicious, but uh

</details>

**Speaker B**: 这种事今天正在发生。是的。

<details>
<summary>Original English</summary>

**Speaker B**: it's happening today. Yeah,

</details>

### 军事应用与武器化机器人

**Speaker A**: 但是，确实存在数据泄露的问题。跟我谈谈军事应用吧。

<details>
<summary>Original English</summary>

**Speaker A**: but it's there's data leakage. Talk to me about military applications.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah,

</details>

**Speaker A**: 北约现在不得不自我武装。我代表美国为我们在北约的立场道歉，但是你们必须付钱，支付你们应分担的份额。你们已经同意这么做了，但我认为在欧洲有一种看法——如果我说错了你可以纠正我——在北约，你们可能不得不在没有美国参与的情况名单干。你们可能需要建立自己的军事产品和服务。难道你们不需要进入军事领域吗？难道你们不应该利用同样的应用去开发军事应用吗？你们现在开始做了吗？

<details>
<summary>Original English</summary>

**Speaker A**: NATO is uh having to arm itself. I apologize on behalf of the United States uh for our stance with NATO, but you guys have to pay up and pay your fair share. You've agreed to do that, but I think there's a perception in Europe, you can tell me if I'm wrong, and in NATO that you may have to go it maybe without the United States. You may need to build your own military uh products and services. Do you not need to be in the military space? And do you not to take the same applications and build military applications? But are you doing that yet?

</details>

**Speaker B**: 是的。所以我觉得欧洲有责任去建立相关技术，以便能够……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So I think there's a responsibility in Europe to build technologies to be able to in

</details>

**Speaker A**: 你个人是这么认为的。

<details>
<summary>Original English</summary>

**Speaker A**: you believe that personally.

</details>

**Speaker B**: 是的。然而，对于我们制造的任何机器人以及我们走上的某条赛道来说，市场需求有巨大的拉力。所以今天我们没有在做这件事，也不打算去做，而且在那个阶段它可能也会是一个不同的产品，对吧。听起来很简单，只需拿一个四足机器人去做军事应用，但你需要深入思考你究竟要在哪些方面做出改变：不同的通信方式，不同的自主性。所以我们没有在做，但我的意思是，我认为我们有责任为他人做这件事。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. However, for any botics we built and we went down one track there's tremendous poll. So today we're not doing it not intend to do it right and it's also a different product at that stage probably right. It sounds very easy just take four legs and do military you need to go a couple of steps for what exactly you're doing different communications different autonomy. So we're not doing it but I mean I think there's a responsibility to do it for others.

</details>

**Speaker A**: 对你来说，是“永远不要说绝对不”呢，还是说你非常坚定，因为你们有自己的使命，所以绝对不打算开发军事产品？

<details>
<summary>Original English</summary>

**Speaker A**: Is it never say never for you uh or is it you're dead set on like you have a mission you're not going to build military product

</details>

**Speaker B**: 对我们今天来说，使命很明确，我们从非军事领域起步，这就是我们的前进方向。

<details>
<summary>Original English</summary>

**Speaker B**: for us today the mission is clear we started with non-military this is where we're headed

</details>

**Speaker A**: 明白了，但是如果欧盟要求你们，并且你们……

<details>
<summary>Original English</summary>

**Speaker A**: got it but if the EU asks you and you

</details>

**Speaker B**: 提出要求的话，我的意思是，我们确实会收到请求，但说实话，我们真的能解决问题吗？仅仅把机器人运给军方并不能解决他们的问题，我们真的需要深入进去，这就意味着你需要一个完全不同的团队来做这件事，我们的团队……

<details>
<summary>Original English</summary>

**Speaker B**: ask I mean we get you know requests but it's also honest truth are we solving actually the problem just shipping a robot to the military doesn't solve the problem yet we really need to go deep so you would need a different team to do that our team

</details>

**Speaker A**: 真的吗，你需要一个不同的团队？感觉你们可以只用同一个团队就能去开发军事应用。

<details>
<summary>Original English</summary>

**Speaker A**: really you need a different team well seems Like you could do the same team and build military applications.

</details>

**Speaker B**: 不行，自主性是非常不同的，对吧？举个例子，我们做自主性功能。你有时间去设置一个机器人，然后它会执行所有的检查任务。而在军事中，一切都在于毫秒必争的远程控制，需要让人类始终在控制回路中。不同的通信方式，不同的自主性。然后上层所有的应用软件也都完全不同。

<details>
<summary>Original English</summary>

**Speaker B**: No, autonomy is very different, right? So for example, we do autonomy. You have time to set up a robot and it does inspections all of that. In military, it's about millisecond being in right remote control human in the loop. Different communications, different autonomy. Then everything on top application software very different.

</details>

**Speaker A**: 是的，你可以使用一个四足机器人进入一座房子。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, you could lose a four-legged robot to also go into a house.

</details>

**Speaker B**: 也仅此而已了，对吧？其余的都不同。

<details>
<summary>Original English</summary>

**Speaker B**: That's about it, right? The rest is different.

</details>

**Speaker A**: 你如何看待带武装的机器人？显然，中国已经展示了同样的带有枪支的四足机器人。显然，随着 AI 的发展，这些类似《终结者》的场景已经变成了现实。

<details>
<summary>Original English</summary>

**Speaker A**: How do you think about robots that are armed? Clearly, China has done demonstrations of these same type of, you know, four-legged robots with guns on them. And obviously with AI, these Terminator scenarios are here.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah,

</details>

**Speaker A**: 它们已经在中国被制造出来了。

<details>
<summary>Original English</summary>

**Speaker A**: they're being built in China already.

</details>

**Speaker B**: 没错。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah,

</details>

**Speaker A**: 我们已经在乌克兰的战场上看到了无人机。挪威离俄罗斯不远。这……

<details>
<summary>Original English</summary>

**Speaker A**: we've seen drones on the battlefield in Ukraine. Norway is not far away from Russia. It's

</details>

**Speaker B**: 也不算太近，但确实也不算太远。

<details>
<summary>Original English</summary>

**Speaker B**: it's not that close, but it's not that far away either.

</details>

**Speaker A**: 对于有些国家正在制造这种装有武器的机器人这一事实，你怎么看？

<details>
<summary>Original English</summary>

**Speaker A**: How do you think about the fact that communist countries are building these robots that have weapons on them?

</details>

**Speaker B**: 嗯，我个人不喜欢。我讨厌它。我认为这很令人担忧，对吧？我的意思是，作为一名工程师，你应该为打造造福人类的技术而感到自豪，对吧。防御是一回事。但主动攻击，在上面装上枪，这实在太危险了。这些技术正在变得成熟，但还没有成熟到你可以让别人因此面临生命危险的地步。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I personally don't like it. I hate it. I think it's concerned, right? I mean, as an engineer, you should have pride, right, to build technology for good. Defense is one part. The active attack, putting a gun on it, it's just risky. These technologies getting mature, but they're not that mature that you would put somebody else in in harm's way.

</details>

**Speaker A**: 是的。我们将要面对的敌人会这么做，我们需要监控这一切。关于这件事，业内有什么传闻吗？当你和行业内的其他人出去交流时，你知道哪些我们不知道的、关于那些国家在机器人技术和军事方面正在发生的事情？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, it is. the enemy we're going to be faced is going to do this and we need to monitor it. What is the buzz inside the industry about this? When you're out with other people in the industry, you know, what do you know that we don't know about what's happening in those authoritarian countries with robotics and the military?

</details>

**Speaker B**: 我认为这些都还是非常早期的测试。如果我看那些视频的话，那些都只是演示而已。

<details>
<summary>Original English</summary>

**Speaker B**: I think these are all very early tests. If I look at those videos, these are demonstrations.

</details>

**Speaker A**: 明白了。

<details>
<summary>Original English</summary>

**Speaker A**: Got it.

</details>

**Speaker B**: 我还没有看到这类机器人投入实战。无人机，是的，在乌克兰，那是出于必需，那是机器人技术中一个已经被成熟使用的类别。实际上，对我交流过的人来说，四年前我们和波士顿动力及其他一些朋友一起写过一封联名信，强烈谴责将机器人武器化，原因正是如此。作为工程师，我们不想看到它被这样使用，我们认为这只是危险、冒险且愚蠢的行为。

<details>
<summary>Original English</summary>

**Speaker B**: I've not seen these types of robot act drones. Yes, Ukraine. that came out of necessity that that was a mature category that was used in robotics. Actually to the people I speak to I mean four years ago we wrote a letter together with our friends at Boston Dynamics and others right who condemn the weaponization of robots for exactly that reason that as engineers we don't want to see it being used and we think it's just dangerous and risky and stupid.

</details>

### 下一位嘉宾介绍

**Speaker A**: 是的。好的。听着，祝你继续成功。各位，非常激动能请到 Bert Borick 来到这里。他是 1X 的创始人兼首席执行官。如果你知道 1X，他们制造了 Neo。Neo 是一款家用机器人。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. All right. Listen, continued success. All right everybody, really excited to have Bert Borick here. He is the founder and CEO of 1X. If you know 1X, they make the Neo. The Neo is a household robot.

</details>

<!-- chunk 3/9 -->

### 交付预期与产品定价

**Speaker A**: 你预售了大量的订单，并且向人们保证这款产品一定能面世，而且会在 2026 年交付到他们的家中。它的价格是多少？你能否达成你自己设定的这个交付期限？

<details>
<summary>Original English</summary>

**Speaker A**: You've sold a lot of pre-orders and you guaranteed people this would make it and would ship in 2026 into their homes. What does it cost? And are you going to hit your self-imposed deadline?

</details>

**Speaker B**: 必须信守承诺。好的。

<details>
<summary>Original English</summary>

**Speaker B**: You got to keep your promises. Okay.

</details>

**Speaker B**: 所以，我们会在 2026 年发货。

<details>
<summary>Original English</summary>

**Speaker B**: So, we will ship in 2026.

</details>

**Speaker A**: 好的。

<details>
<summary>Original English</summary>

**Speaker A**: Okay.

</details>

**Speaker B**: 现在，我们要在这里做一下预期管理。前期的进展会比较慢。我们希望把事情做好。是的。但是会有一小部分客户在 2026 年拿到他们的 Neo，我真的非常激动，我已经等不及了。

<details>
<summary>Original English</summary>

**Speaker B**: Now, expectation managing here. It'll be slow in the beginning. We want to do it right. Yes. But there will be a handful of customers that get their Neo in 2026 and I'm so excited and I can't wait.

</details>

**Speaker A**: Neo 的价格是多少？

<details>
<summary>Original English</summary>

**Speaker A**: What is the cost of the Neo?

</details>

**Speaker B**: 这是一个很有意思的问题，因为它视情况而定。嗯，我的意思是，当我们推出预购时，我们有两种不同的付款模式。一种是类似于早期采用者的预先全额付款，嗯，另一种是我们收取订阅费，而且产品当然还在经历大量的开发过程。所以这种订阅模式将会是什么样子，以及这些具体细节，都还在不断演变之中。我们希望在早期也能和客户一起摸索出这些方案；但现在还有另一件大事，我们还没真正宣布过，不过我之前稍微透露了一点点——那就是我们将允许很多人在 Neo 上进行开发，所以我们也会把 Neo 作为一个平台来发布。

<details>
<summary>Original English</summary>

**Speaker B**: So that's an interesting one because it depends a bit. Um I mean when we launched the pre-order we had two different payment models. You had a kind of like early adopter upfront full payment um and then we had a subscription fee and the product of course is going through a lot of development. So how this subscription model will look and these things are kind of like still evolving and we want to figure that out also a bit together with our customers in the beginning but another big one now is we haven't really announced this yet but uh I've dripped it in a bit which is we are going to allow a lot of people to build on Neo so we are also launching Neo as a platform

</details>

### Neo 作为一个开放平台与生态系统

**Speaker A**: 是的，我想到了类似于应用商店（App Store）或者技能商店之类的东西。所以，如果我家里有一台，然后我想做个沙拉，你作为一个黑客可以开发一个沙拉技能，然后我就可以购买并订阅你的沙拉技能。对吧，

<details>
<summary>Original English</summary>

**Speaker A**: yes I'm thinking app store of such or a skill store so if I have it in my home and I want to make a salad you as a hacker could make the salad salad skill and I can buy and subscribe to your salad skill. Yeah,

</details>

**Speaker B**: 这将是其中的一部分。但对我来说，NEO 和 1X 远不止是针对消费者市场，对吧？消费者当然是一个极其重要的市场，但 1X 一直以来的愿景是，我们如何通过这些人形机器人为整个社会创造丰富的劳动力。我真心相信，我们现在拥有了一个非常独特且极具优势的平台，如果允许人们在这个平台上进行开发，将会彻底打开 Neo 在我们整个社会中的应用场景，而不仅仅是在家庭里，对吧？而且这也将使消费者受益，因为这意味着会有更多在 Neo 上开发出来的东西；其中一部分将会是面向消费者的应用商店，对此我们感到非常兴奋。但总体而言，这也是关于你如何创建一个更大的生态系统，这个生态系统能够加速自治能力的发展，并加速我们真正在家中拥有一个完全自主并能包揽一切的智能体的进程。

<details>
<summary>Original English</summary>

**Speaker B**: that will be part of it. But to me, NEO and 1X is about so much more than just consumer, right? So consumer is an incredibly important market, but 1X has always been about how do we create an abundance of labor across society through these humanoids. And I sincerely believe that we have a platform now which is so uniquely capable and so well situated that allowing people to build on this will open up how to use Neo across all of our society not just in homes right but it will also benefit the consumer because this will mean there will be more things developed on Neo and part of that will be an app store targeted towards consumer which we're very excited about but also it will just be in general how do you create a bigger ecosystem that can just accelerate the autonomy and accelerate the path to actually having a fully autonomous agent at home that can do it.

</details>

**Speaker A**: 预购量是多少？2万台还是多少来着？我试着回忆一下。

<details>
<summary>Original English</summary>

**Speaker A**: What was the pre-order? 20K or something. I'm trying to remember.

</details>

**Speaker B**: 我们还没有公布官方数据，但这是一个相当可观的数字。我们在最初的几天里就卖光了首批的 1 万台。

<details>
<summary>Original English</summary>

**Speaker B**: So, we have we haven't given out official numbers, but it's pretty significant. We s we sold out the first 10K in uh the first few days.

</details>

**Speaker A**: 哦，所以人们为此支付了订金。他们将能够完全... 所以这有点像特斯拉的 500 美元订金，或者是每个月 500，每个月 1000，差不多这个范围。对，每个月 500。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, so people put a deposit down for that. They'll have the ability to fully uh so sort of like the Tesla $500 deposit or 500 a month, a,000 a month, something in that range. Yeah, 500 a month.

</details>

**Speaker B**: 每个月 500。

<details>
<summary>Original English</summary>

**Speaker B**: 500 a month.

</details>

**Speaker A**: 所以，这就像，如果让我找个参照物，就像谷歌眼镜（Google glasses）或者是 Vision Pro。这是为那些高端人群准备的，他们是先锋，是最早的一批尝鲜者（early adopters）。对吧，

<details>
<summary>Original English</summary>

**Speaker A**: So, this is for, if I were to think of a parallel Google glasses or the Vision Pro. This is for high-end folks who are the Vanguard, who are the earliest of the early adopters. Yeah,

</details>

**Speaker B**: 百分之百。我的意思是，我们试图对此保持非常透明的态度。在 2026 年拿到一台家用人形机器人，它肯定会有很多粗糙不完美的地方，对吧？它们会摔倒。它们会摔倒，对吧？呃，但我很高兴地说，我认为我们实际上将能够交付一款非常接近完全自主的产品，这是我们在发布时不想做出的承诺，因为当时还为时过早；但我...我现在也不想完全承诺这一点，但从现在的发展趋势来看，我们似乎将能够交付一种完全自主的体验，而且那也是相当有用的。当然，如果你希望第一天所有东西都能开箱即用，那么它将会涉及一些远程操作（teleoperation）或者对系统的某些指导。但最近真正让我感到兴奋的是，我们现在看到了实际交付这种产品的路径，也就是说，如果你想要的话，它可以是一个完全自主的体验，而且它正变得相当不错。

<details>
<summary>Original English</summary>

**Speaker B**: 100%. I mean, we tried to be very transparent about this. Getting a home humanoid in 2026 is going to be rough around the edges, right? They're going to fall. They're going to fall, right? Uh but I am very happy to say that I think we will actually be able to ship something that's very close to full autonomy which we did not want to promise when we launched this because it was too early but and I I'm not going to fully promise it yet but the way it's trending now it looks like we will be able to ship an experience that is fully autonomous and that is still quite useful. Now, if you want everything to just work out of the box day one, then there will be some teleoperation involved or some guidance of the system. But a thing that really excites me these days is that we're seeing the path now to actually shipping something that if you want it, it can be a fully autonomous experience and it's getting pretty darn good.

</details>

### 远程操作（Teleoperation）的潜力

**Speaker A**: 远程操作（tea operating / teleoperation）对我来说非常迷人。我不知道你有没有看到这个新闻，在纽约有一家鸡肉三明治店。他们找不到... 呃，收银员。所以他们在菲律宾的马尼拉雇了个人，你知道的，每小时 3 美元，这对菲律宾的收银员来说是一份非常丰厚的薪水。然后他们让她通过 Zoom 通话工作。他们只是打开了 Zoom，他们自己来操作它，然后你就可以点餐，如果你遇到客服问题，你直接和她说话，她就会说：“嘿，我就在这里。”在某种程度上，这也就是你能用你的机器人做的事情。你可以在菲律宾有一个人，你可以连线到他们，他们能够开启它，当你说“嘿，给我倒杯橙汁”的时候。那个人就能远程完成那个任务。我是不是正确地设想了这个场景，还是我想错了？

<details>
<summary>Original English</summary>

**Speaker A**: The tea operating is fascinating to me. I don't know if you saw this, but in New York there was a chicken sandwich shop. couldn't find um a cashier. So, they hired somebody in Manila in the Philippines for, you know, $3 an hour, which is a huge salary for a for a cashier in the Philippines. And they had her on a Zoom call. They just popped up Zoom, acted it themselves, and you could order and if you had a customer service issue, you just talked to her and she was like, "Hey, I'm right here." That is in some ways what you'll be able to do with your robot. You'll have somebody in the Philippines who you'll be able to tap into who'll be able to turn it on and when you say, "Hey, pour me a glass of orange juice." That person will be able to remotely do that task. Is is that what I'm envisioning here correctly or incorrectly?

</details>

**Speaker B**: 我觉得这些都会发生。所以...所以，回到这个平台是如何运作的，对吧？让我稍微退一步，花大概两分钟时间谈谈这个。如果你把 Neo 当作一个平台来想，所以如果你想围绕这家橙汁店建立你的店面，好的，你买了一批 Neo，你拿到了 Neo，你获得了带有车队管理等功能的机器人操作系统。你还获得了数据收集设备，那是一双拥有与 Neo 相同的触觉传感器、相同的视觉系统的手套，然后你就可以在你的店里收集数据，对吧？在我们的系统内微调（fine-tune）我们的模型，在里面我们有点像是...我们为你做所有数据的密集标注（dense captioning），就像我们做所有的这些工作，你微调你的模型，你部署它，然后你让它跑起来，现在你有了一家全自动的商店，你非常开心。这是一条路径。也许那个方案不太行得通，所以你说，啊，我打算让某个人有时通过远程操作（tallyop / teleop）介入，然后你的数据就会变得更好。这也是一种做法，对吧，收集数据有很多种方法。或者也许你只是说，你知道吗，这太复杂了，我只想要完全远程对话控制的。那也没问题。这取决于你想如何应用它。嗯，而且这个平台覆盖了从那些只想自动化其工作流程的开发者，一直到那些想要部署他们自己模型的基础研究实验室。所以，也会有这样一种情况，你可以在 Neo 上运行别人开发的模型。我想，我们将允许这样做。呃，

<details>
<summary>Original English</summary>

**Speaker B**: I think it will all happen. So so so back to how the platform works, right? So let me just back up and spend like two minutes on that. So if you think about Neo as a platform, so if you want to build your orange shop around this orange juice shop that okay, you buy a bunch of Neos, you get Neos, you get the robot operating system with like the fleet management and all that. You also get the data collection equipment which is gloves that have the same tactile sensors as Neos, the same vision system, and you can gather data in your shop, right? fine-tune our model with within our system where we kind of like we do all the cap dense captioning of the data for we you like we do all that you fine tune your model you deploy this and you get this working and now you have a fully automated shop and you're very happy that's one path maybe that doesn't quite work so you say ah I'm going to have someone intervene sometimes in tallyop and then your data gets better that's one way of doing it right there's many ways of gathering data or maybe you're just saying like you know what this is super complicated I just want it fully talked. That's also fine. Depends on how you want to apply this. Um, and the platform goes all the way from like these kind of like developers that just want to automate their workflow all the way to the more foundation labs that want to deploy their models. So there's also a world where you can run someone else's model on Neo. We're going to allow that, I think. Uh,

</details>

**Speaker A**: 所以你们将成为一个开放平台。从某种意义上说，你们在内部知识方面将是“无头”（headless）的。你将能够接入外部模型，如果 OpenAI 有一个世界模型，或者 Claude，或者其他一些独立的世界模型，它们将能够被接入。对，

<details>
<summary>Original English</summary>

**Speaker A**: so you're going to be an open platform. You'll be in a way headless to the knowledge inside of it. You'll be able to plug in if OpenAI has a world model or Claude or some of the other independent world models, they'll be able to be plugged in. Yeah,

</details>

**Speaker B**: 百分之百。不过，我真心相信我们的模型会是最好的那一个。

<details>
<summary>Original English</summary>

**Speaker B**: 100%. Now, I sincerely believe that our model will be the best one.

</details>

**Speaker A**: 当然。

<details>
<summary>Original English</summary>

**Speaker A**: Sure.

</details>

**Speaker B**: 而且我相信竞争。所以，如果我们这个真正从制造一直掌控到产品的团队，却不能做出最好的模型，那我们就有点算是失败了。

<details>
<summary>Original English</summary>

**Speaker B**: And I believe in competition. So, if we that actually control everything from the manufacturing all the way up to the product can't make the best model, then we kind of failed.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 呃，但是我们会允许其他人在此基础上进行开发吗？百分之百会。这背后的一个重要原因是，如果你看看目前这个领域的发展现状，目前并没有一个能够解决机器人领域所有问题的通用模型。现在还没到那一步，对吧？如果我们被困在客户类似后院的地方，在接下来的几年里帮他们整合 ERP 解决方案以及其他所有事情，我们将无法实现目标。我们想做的是解决通用性问题。我们如何解决具身人工智能（embodied AGI）问题，以便我们能够真正创造出丰富的劳动力？这就要求我们专注于通用问题，然后允许其他人也来帮助应用今天现有的技术，并帮助建立生态系统。对吧？如果我们能建立起这个庞大的机器人生态系统，我们所有人都会受益。

<details>
<summary>Original English</summary>

**Speaker B**: Uh but will we allow other people's to build on this? 100%. And one of the big reasons for this is that currently if you look at where this where the field is, there is no one general model that solves everything for robotics. It's not there yet, right? And if we are stuck in our customers kind of like backyards helping them integrate towards ERP solutions and everything else the next couple years, we are not going to get there. What we want to do is to work on the general problem. How do we solve embodied AGI so we can actually create an abundance of labor? And this requires us to focus on the general problem and then allow other people to also help apply what is available today and to help build the ecosystem. Right? If we get this enormous robotics ecosystem, we all benefit.

</details>

**Speaker A**: 是的。我可以看到一些应用场景，只需一名远程操作员（TA operator），假设这是一个便利店机器人，只是帮你把东西搬到你的车上。这可能每小时才发生一次。你可以配备一名远程操作员（tea operator），或者你可能有 10 名操作员在监控 30 到 40 台 Neo，他们远程控制这些机器人，帮助人们把杂货搬到他们的车上。对，

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And I could see some applications where one TA operator, let's say this was a convenience store robot that just help you carry stuff out to your car. That might only happen once every hour. You could have one tea operator or maybe you have 10 of them that are monitoring 30 40 Neos and they control them remotely and help people move the groceries to their car. Yeah,

</details>

**Speaker B**: 实际上，就我个人而言，我... 就像我有一个针对 Neo 的使用场景。好吧，在远程操作（Talop）方面，那就是我一部分时间待在挪威，现在大部分时间在旧金山湾区，但也有一部分时间在挪威，而且我还有点像是要参加这种会议，对吧？当我在外旅行的时候，我希望能够有“在场感”并且运营我的...

<details>
<summary>Original English</summary>

**Speaker B**: personally actually I'm I'm like I have a use case for Neo. Okay, in Talop, which is I'm part of the time in Norway, mostly in San Francisco area now, but part of the time in Norway and I'm also kind of like conventions like this, right? And when I'm out traveling, I want to be able to be present and run my

</details>

<!-- chunk 4/9 -->

### 远程操作与数据金字塔

**Speaker A**: 给Neo戴上设备，我就是Neo。这其实非常神奇。我能到处走动，能拿起零件，也能检查零件。我还能跟人说话，参加会议。这就是远程操作的一个应用场景，我认为它永远不会消失。无论你的自主性有多高，这种需求始终都会存在。

<details>
<summary>Original English</summary>

**Speaker A**: Put the hat on Neo. I am Neo. And that's actually pretty magical. And you can I can go around. I can pick up the parts. I can look at the parts. I can talk to people. I can be in the meetings. Right. And so that's one application of teleoperation that I think actually will never go away. Like no matter how good your autonomy is, that will still be there.

</details>

**Speaker B**: 是的。就比如你在深圳工厂里的化身。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Your avatar at your factory in Shenzhen.

</details>

**Speaker A**: 百分之百是这样。

<details>
<summary>Original English</summary>

**Speaker A**: 100%.

</details>

**Speaker B**: 没错。你也知道，还有一些像偏远发电站这样的应用场景，比如附近一小时车程内都荒无人烟。你在机房里放个机器人，一旦出问题，你就可以远程操控它去拉下旧开关，做些处理。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And you know there are other applications like this where remote power stations where there's no one within like an hour of driving. You have a robot standing in the closet and something goes wrong and you go out and you like flip the old switches and you do the things

</details>

**Speaker A**: 像这种场景你很可能不会去实现完全自动化，因为它属于那种好几个月才会发生一次的偶发事件，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: like you're likely not going to automate that because it's kind of like a one-off thing that happens every few months. Right.

</details>

**Speaker B**: 没错。但把机器人安置在比如森林深处的电力线路或变流器旁边，是非常值得的。它们可以在几分钟内出动并开始工作。这本质上就像过去所说的“就地专家”（expert in place）概念——你可以把世界上最顶尖的专家瞬间“传送”到全球任何地方去协助解决问题。

<details>
<summary>Original English</summary>

**Speaker B**: Right. So, but it's worth having that robot in that space out in the middle of the forest near, you know, those power lines or power converters. They can go out within, you know, minutes and and work. Essentially like what used to be called like expert in place, like this concept of like you can take the world's best expert and tell teleport them to anywhere in the world to help solve a situation

</details>

**Speaker A**: 就像外科医生一样，对吧。

<details>
<summary>Original English</summary>

**Speaker A**: like a surgeon. Yeah.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 这真的非常实用。不过我认为，过去一年我们体会最深的是，首先，Neo的能力变得非常强，特别是有了新的双手之后，仅仅依靠人类进行远程操作已经无法完全发挥硬件的潜能了。也就是你无法让远程操作足够好，来充分利用这些硬件。

<details>
<summary>Original English</summary>

**Speaker A**: It's it's super useful. I do think that what we've experienced over the last year is first of all that Neo has become so capable especially with the new hands that teleoperation does not fully use the hardware like you're not able to get the tele operation to be good enough to fully utilize the hardware.

</details>

**Speaker B**: 也就是说，机器手具备的灵敏度，已经超过了远程操作员所能发挥的水平。

<details>
<summary>Original English</summary>

**Speaker B**: Uh so the fidelity of the hand is greater than a teller operator is able to leverage.

</details>

**Speaker A**: 没错。比如，操作员的触觉和机器人所感受到的不一样。那么你就需要去构建一套完整的触觉反馈系统，但这会拖慢你的速度，让整个系统变得迟钝笨重。因此，我们越来越多地发现，让人类尽可能无感地穿戴机器人的传感器去收集数据，才是最好的。它们不应该干扰你正在做的事情，这是为了解决机器人基础灵巧性最有用的数据。但更重要的是我们在1X立下的长达十年的重注：如果你能让机器人足够像人，那你就可以直接使用现有的海量人类视频数据来训练它们。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Right. The teleoperator will not feel the same as the robot is feeling for example. Right. then you need to build full haptic systems and they're going to slow you down and be slow and clunky and like so we're increasingly seeing that gathering data with humans just wearing the sensors of the robot in as transparent a manner as possible. So like they should not disturb what you are doing right that's the most useful data to solve kind of baseline dexterity on the robot but even more importantly the big bet that we made which is this decade long bet in 1x is if you get the robot to be similar enough to a human then you can train on all of the available video data out there of humans.

</details>

**Speaker B**: 确实。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 而且我们已经开始看到一些非常好的证据表明这确实效果惊人。这也是我们成立世界模型实验室（World Model Lab）的原因，因为我们在这一点上终于实现了缩放定律（scaling loss）。而且我们正在看到这种趋势。

<details>
<summary>Original English</summary>

**Speaker A**: And we're starting to see some very good proof that this is actually working incredibly well. And that's the reason we started the WX World Model Lab because we now finally have the scaling loss on that. And we're seeing that this

</details>

### 数据护城河与跨具身智能

**Speaker B**: 让我们深入了解一下实验室内部的情况吧。你们是让人在工厂里戴着眼镜、穿戴着设备日复一日地执行任务吗？你们有没有雇人去真实世界中执行任务，以此来外包积累那些其他公司没有的专有数据集？世界模型到底是如何在规模上建立起来的？

<details>
<summary>Original English</summary>

**Speaker B**: take us inside that take us inside the lab. You are you having people in factories wear glasses, wear your hands, and do their tasks over and over again? Are you working with the micro ones of the world to go do you know real world stuff and outsourcing like unique proprietary data that you can have that other companies don't? How does the world model get built at scale?

</details>

**Speaker A**: 首先，我们确实有这么做，但这并不是核心。我认为归根结底道理很简单，模型的好坏取决于数据。

<details>
<summary>Original English</summary>

**Speaker A**: So so so first of all yes we do that and if you but that's not the main point. So I think ultimately it's very simple right the model is going to be as good as the data.

</details>

**Speaker B**: 嗯。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 如果你把数据看作一个金字塔，那么最顶层是远程操作数据。这是一种质量非常高、规模很小且精调过的数据集。在这个过程中，操作员会尝试又快又好地执行任务，他们经常会失败，然后再试一次，我们只保留那些他们能像人类一样完美完成任务的优良样本。你不需要海量的这种数据，它只是用来对齐你的模型的。接着下一层就是你刚才提到的数据类型，也就是让人类穿戴传感器去收集的数据。

<details>
<summary>Original English</summary>

**Speaker A**: And if you think about the data pyramid then on the top you have like tele operation data very high quality small fine tuned data set where actually what we do is you will have the operator try to do the task very well and very fast and they will often fail and then just try again and then we pick the good samples where they did the task as good as a human would right you don't need a lot of that data it's just to align your model then you have the data which is what you're talking about with like put the sensors on the human go and gather data.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah,

</details>

**Speaker A**: 这种数据量会更大一些，而且它和机器人的实际情况非常接近，但本质上还不是机器人在操作。这是替身操作。再往下，你有从人类第一视角（egocentric）拍摄的视频数据。这离机器人又远了一步，但依然相当接近，因为机器人的手和人类的手在视觉和结构上都是一样的。然后就是普遍的通用视频数据。

<details>
<summary>Original English</summary>

**Speaker A**: you have more of that and it's very close to the robot but it's not the robot. The telea is the robot. This is not the robot but it's close. Then you have egocentric video from humans point of view. So that is further away from the robot but it's still quite close because the robot hands is the same as human hands and like it looks the same and so it's quite close. And then you have general video data.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 关于这个世界，或者说关于人类活动的通用视频。因为Neo和人类如此相似，我们其实能够利用所有这些数据。而位于金字塔底层的这些通用视频数据，其规模与其他层级相比，简直是庞大得令人觉得荒谬。

<details>
<summary>Original English</summary>

**Speaker A**: Of the world. or the world in general and of people, right? And because Neo is so similar to a human, we can actually utilize all of that data. Now, the bottom layer in the pyramid, which is this video data, general video data is absolutely ludicrously immense compared to anything else.

</details>

**Speaker B**: 包括YouTube，包罗万象。

<details>
<summary>Original English</summary>

**Speaker B**: It's YouTube, it's everything.

</details>

**Speaker A**: 所以如果你看看要实现真正的智能到底需要什么，你会发现你需要的数据量，比任何人未来几年通过第一视角或传感器收集到的数据量要多出好几个数量级。

<details>
<summary>Original English</summary>

**Speaker A**: So if you look at what is needed to actually achieve true intelligence, you need multiple orders of magnitude more data than anyone is even close to collecting over the next few years with egocentric data or with this sensor data.

</details>

**Speaker B**: 明白了。

<details>
<summary>Original English</summary>

**Speaker B**: Got it?

</details>

**Speaker A**: 据我所知，人工智能领域所有重大的突破，都是因为有人找到了方法去利用以前无法利用的庞大新数据源。一旦你解锁了某类新的数据集，你模型的能力就会大幅提升。

<details>
<summary>Original English</summary>

**Speaker A**: And all of the major breakthroughs that we've seen as far as I'm aware of in AI have been because someone figured out how to use a huge new data source that previously we were not able to use. you unlock some new set of data and now your model capability greatly improves.

</details>

**Speaker B**: 可是现在有很多人都在试图寻找这样的数据，这可能需要花上好几年时间。

<details>
<summary>Original English</summary>

**Speaker B**: Well, you've got a lot of people out there trying to find data like that is like one of the gonna take years.

</details>

**Speaker A**: 这就像是个第22条军规（死循环）。所以我们的重大押注在于：你必须能够利用互联网上现存的通用视频数据。

<details>
<summary>Original English</summary>

**Speaker A**: So, it's it's like a catch 22. So, our big bet is you have to be able to utilize the general video data out there.

</details>

**Speaker B**: 嗯。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 而实现这一目标的唯一途径，就是你必须关注机器人的每一个微小细节，让它尽可能地接近人类。你知道，像肌肉、组织和皮肤……

<details>
<summary>Original English</summary>

**Speaker A**: And the only way to do that is you have to care about every single tiny detail of the robot to be as close to human as possible. Like you know like the flesh and tissue and skin

</details>

**Speaker B**: 没错。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 这些是高度非线性的。比如，它变形需要多大的力？摩擦力是多少？触摸桌子时的冲击能量是怎样的？

<details>
<summary>Original English</summary>

**Speaker A**: is highly nonlinear. So like how much force for it to deform? What's the friction? Like what is the impact energy when touching the table?

</details>

**Speaker B**: 而且不同人的手大小也不同。在NBA里甚至有“臂展”这个概念，那些臂展比普通人长两三英寸的球员，薪水能多拿20%。细想起来这还挺有意思的。

<details>
<summary>Original English</summary>

**Speaker B**: And people have different size hands. I mean literally in the NBA there's a wingspan as a concept and people with a wide wingspan, longer arms than the average person get paid 20% more for having that extra two or three inches of wingspan. It's pretty fascinating when you think about it.

</details>

**Speaker A**: 臂展是个很好的说法。我们一直把它叫做“大猩猩系数”（gorilla coefficient）。长手臂。

<details>
<summary>Original English</summary>

**Speaker A**: That that's a really good way of saying it. Wingspan. We've always we've always called it for the the the gorilla coefficient. Yes. Long arms.

</details>

**Speaker B**: 哈哈。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 是的。所以我的观点是，虽然我们也做所有这些事，但从根本上讲，1X与其他所有机器人公司最大的区别在于，我们全押在利用互联网视频数据预训练我们的模型上。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. If you But but anyway, yeah. So, my point is, yes, we do all of these things, but ultimately what differentiates 1X from all of the other robotics companies is that we are all in on pre-training our own models on this video data on the internet.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 而且我们的“跨具身”（cross embodiment）不是指另一个机器人，我们的跨具身对象就是人类。我们希望尽可能接近人类，因为这能打破刚才那个死循环。最终，所有的数据都会是机器人数据，因为机器人数据包含动作、触觉、力反馈，质量更高。但获取所有这些数据的唯一途径，就是你要先创造一个足够强大的基础模型，把这些机器人部署到社会中去，让它们去做人们愿意付费的有用工作，同时在过程中顺便收集数据。

<details>
<summary>Original English</summary>

**Speaker A**: And that our cross embodiment is not another robot. Our cross embodiment is the human. And we want to be as close to that as possible because that solves the catch 22. In the end, all the data will be robotics data because a robotic data has it has the actions, it has the tactile, it has the forces, it's better. But the only way to get all of that data is to create a base model that is good enough that you can deploy all these robots across society and they will do useful things that people pay for and also gather the data.

</details>

### 自主智能与未来的机器人

**Speaker B**: 什么时候机器人会变得具有递归性，能够自我学习、自我构建呢？就像我们现在看到的大语言模型一样，人们现在开始创造智能体，不再只是给它们提示词和指令，而是说：“这是你的目标，这是你的工作循环。你是一个负责为企业寻找潜在客户的智能体。好的，你是另一个负责客户成功的智能体，这是你的工作范畴。还有你，是负责产品定价的智能体”，然后这些智能体会协同工作。我们已经在知识工作领域看到了这种趋势。这种趋势什么时候会来到机器人领域？到时候你都不需要去操心如何让机器人变得更好，因为它们足够有感知力（或许这个词不准确，但它们知道自己的使命）。你只要给它们定个目标，比如：“嘿，你在一家米其林星级餐厅工作，你的目标是用这种保真度和完美度做出最美味的食物。”然后告诉它结果，它就会说：“好的，为了做得更好，我只需要在煮鸡蛋上多下点功夫。”

<details>
<summary>Original English</summary>

**Speaker B**: When do the robots become recursive in nature and they are teaching themselves, building themselves and like we're seeing with large language models now where people creating agents instead of giving it prompts and instructions we're now starting to say well here are the goals here's a loop you are one agent that you know identifies for a business potential customers okay you're the agent that does customer success and here's what that looks like you're the agent that uh you know does pricing of products and those agents start working in concert. We're starting to see that in knowledge work. When does that come to robotics where you don't have to actually worry about making the robots better? They're sentient enough to use a word. Perhaps not accurate, but they know what their mission is. You've given them the goal. Hey, you're working in a Michelin starred restaurant. your goal is to make the most delightful food with this level of fidelity and perfection. Um, and here are the outcomes. And it says, "Okay, I've just got to get better at, you know, uh, poaching these eggs to to really be great at this."

</details>

**Speaker A**: 这听起来有点科幻了。不，这不是科幻。这其实是我们思考了很多的问题，但这也是一个极难回答的问题，因为你也知道，目前的发展正处于这样的一条曲线上，而你刚好在这个曲线上。所以当你问我……

<details>
<summary>Original English</summary>

**Speaker A**: It's kind of sci-fi. No, no, it's not sci-fi. It's actually something we think a lot about, but it's also incredibly hard to answer because, you know, the development now is going like this and you're here on the curve. So when you asked me a

</details>

<!-- chunk 5/9 -->

### AI的硬起飞与商业化预期

**Bernt**: 一年前，对于今天我们在人工智能领域能走多远，我还要悲观得多。而且似乎每次我抽样观察，事情的进展都比我想象的要快。所以，我们很容易得意忘形，对吧？但我想如果我试着宽泛地回答这个问题，我非常确信，距离“硬起飞”（hard takeoff）已经不到十年了。我所说的硬起飞，是指机器人制造机器人、数据中心和芯片工厂，并进行采矿和提炼。实现真正的劳动力充裕，一个能够自给自足的系统只需不到 10 年的时间。

<details>
<summary>Original English</summary>

**Bernt**: A year ago, I was way more bearish on how far along we would be today on the AI and like every time I kind of sample things have moved faster than I think. So it's easy to get like carried away, right? But I think if I try to answer it broadly, I am extremely sure that we're less than a decade away from hard takeoff. And when I say hard takeoff, I mean robots building the robots, the data centers, the chip fabs, doing the mining and refining. Actually a true abundance of labor, a self-sufficient system that is just under 10 years.

</details>

**Host**: 不到 10 年。

<details>
<summary>Original English</summary>

**Host**: Under 10 years.

</details>

**Bernt**: 我目前的猜测是 3 年。

<details>
<summary>Original English</summary>

**Bernt**: Under 10 years, my current bet would be 3 years.

</details>

**Host**: 明白了。

<details>
<summary>Original English</summary>

**Host**: Got it.

</details>

**Bernt**: 但即使需要 10 年，在人类历史的长河中，对吧？这也只是一瞬间。这其实无关紧要。这又回到了“什么是 1x”的问题，对吧？因为……

<details>
<summary>Original English</summary>

**Bernt**: But like if it takes 10 like in the history of humanity, right? It's still like a blip. It doesn't really matter. That gets back to like what is 1x, right? Because...

</details>

**Host**: 而且你把这称为行业术语“硬发布”（hard launch）或者……

<details>
<summary>Original English</summary>

**Host**: And you call this the industry term hard launch or...

</details>

**Bernt**: “硬起飞”（hard takeoff）。

<details>
<summary>Original English</summary>

**Bernt**: hard takeoff.

</details>

**Host**: “硬接管”（Hard takeover）。

<details>
<summary>Original English</summary>

**Host**: Hard takeover.

</details>

**Bernt**: “起飞”（Takeoff）。不是接管（take over）。我们会妥善处理的。所以它会是硬起飞。

<details>
<summary>Original English</summary>

**Bernt**: Takeoff. Not take over. We're going to do it right. So it's going to be hard take off.

</details>

**Host**: 硬接管。是的。

<details>
<summary>Original English</summary>

**Host**: Hard takeover. Yes.

</details>

**Bernt**: 但你知道我听过这个词，对，这是一个行业术语。没有物理实体，你其实无法实现这一点，对吧？就像数字智能永远无法创造自己的物理载体一样，你需要物理实体。而且我认为这也将在促进科学进步等方面对人类产生难以置信的影响，对吧？就像我们现在在平台上看到的很多需求，都是那些想要自动化实验室工作的人，因为如果你的 AI 模型不能真正建立并执行它的实验并观察结果，它们如何能推动科学进步？对吧。所以所有这些事情都将在未来几年内发生，随着 AI 变得物理化，确切的时间线很难说，但这是以“年”而不是“十年”来计算的。

<details>
<summary>Original English</summary>

**Bernt**: But you know I've heard the term right this is a industry term. And you can't really get this without the physical part right like the digital intelligence can never create its own substrate you need the physical part, right. And I think also this is going to have incredible impact on humanity with respect to for example progressing science right, like a lot of the demand that we're seeing now on our platform is people who want to automate lab work, because if your AI model can't actually build and carry out his experiments and observe the results. How are they going to progress science? Right. So all of these things will happen in the coming years as AI becomes physical and exact timeline is a bit hard but it's years not decades.

</details>

**Host**: 是的。我的意思是，如果你相信是 3 年，我知道你是个乐观主义者，要从事你现在做的事情，你必须是个十足的疯狂乐观主义者，而且你认为最保守的估计是 10 年，那么 5 年、6 年或 7 年对我们来说也就很好了。Bernt，你得赶飞机了。这太棒了。祝你继续成功。如果人们想订购一台 Neo，每个月给你 500 美元来参与你正在做的这个绝对疯狂的事业，他们该怎么做？他们如何加入？

<details>
<summary>Original English</summary>

**Host**: Yeah. I mean, if you believe it's three, and I know you're an optimist, you have to be to do what you're doing, a crazy optimist for sure, and you think the outer, you know, estimate is 10, you know, we'll be fine with five, six or seven. Bernt, you've got to catch a flight. This is amazing. Continued success. If people want to order a Neo and give you $500 a month to be part of this absolute lunacy that you're doing, what do they do? How do they get in?

</details>

**Bernt**: 嗯，你可以去我们的网站订购一台 Neo。

<details>
<summary>Original English</summary>

**Bernt**: Well, you go to our website and you order a Neo.

</details>

**Host**: 就这样？就这么简单。现在是 2026 年，本来就应该这么简单。

<details>
<summary>Original English</summary>

**Host**: That's it. It's that simple. It's 2026. It should be that simple.

</details>

**Bernt**: 本来就应该这样，对吧？如果你能在网上订购特斯拉，你就能在网上订购 Neo。价格透明。

<details>
<summary>Original English</summary>

**Bernt**: It kind of should, right? If you can order a Tesla online, you can order a Neo online. Transparent pricing.

</details>

**Host**: 我喜欢。是的。Bernt，祝你继续成功。

<details>
<summary>Original English</summary>

**Host**: I like it. Yeah. Uh, Bernt, continued success.

</details>

### Plaude 广告赞助

**Announcer**: 在你的世界里，每一个字都很重要。尽职调查电话上的数字，董事会会议上的承诺。Plaude 能够捕捉对话，并将其转化为可在几秒钟内提取的可搜索情报。向 Plaude 提问，无需收据即可获得答案。停止翻阅录音或轻信你的记忆。捕捉对话。保留信号。这就是 Plaude。欲了解更多信息，请访问 plaude.ai。

<details>
<summary>Original English</summary>

**Announcer**: In your world, the exact words matter. The number on the diligence call, the commitment in the board meeting. Plaude captures a conversation and turns it into searchable intelligence you can pull up in seconds. Ask Plaude a question and get the answer with no receipt. Stop scrolling recordings or trusting your memory. Capture the conversation. Keep the signal. That's Plaude. Learn more at plaude.ai.

</details>

### 波士顿动力的现状与商业化部署

**Host**: 好了，大家好。我们非常幸运。今天请到了 Amanda McMaster。不是 McMasters。是 McMaster。

<details>
<summary>Original English</summary>

**Host**: All right, everybody. We're really lucky. We have Amanda McMaster here. Not McMasters. McMaster.

</details>

**Amanda McMaster**: 只有 McMaster。没有 s。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Just McMaster. No.

</details>

**Host**: 只有 McMaster。没有 McMasters。你是波士顿动力（Boston Dynamics）的临时首席执行官，这是一家元老级、最初的机器人公司。几十年来，我们一直看到你们的机器人在做后空翻、中国功夫，被踢被打后还能站起来。我们甚至很难记住现在这家公司到底是谁的，因为它曾经是一家独立的初创公司，后来被谢尔盖（Sergey）和拉里（Larry）买下。它曾是谷歌的一部分，然后又被卖掉了。我想孙正义（Masayoshi）曾在某个时候拥有过它，但我相信现在它是现代（Hyundai）的。

<details>
<summary>Original English</summary>

**Host**: Just McMaster. No McMasters. Uh, you're the interim CEO of Boston Dynamics, the OG, the original robotics company. The robots we've seen for decades doing back flips, doing kung fu, getting kicked and beaten, and getting back up. We have been having a hard time remembering who owns this company now because it was an independent company, venturebacked, then Sergey and Larry bought it. It was part of Google, then it got sold. I think Masayoshi owned it at some point, but I believe Hyundai owns it now.

</details>

**Amanda McMaster**: 没错。

<details>
<summary>Original English</summary>

**Amanda McMaster**: That's correct.

</details>

**Host**: 我把这整个历史都说对了吗？

<details>
<summary>Original English</summary>

**Host**: Did I get that whole history correct?

</details>

**Amanda McMaster**: 说对了。完全准确。

<details>
<summary>Original English</summary>

**Amanda McMaster**: You did. You nailed it.

</details>

**Host**: 好的。显然我看了太多行业新闻，但现在你负责这块了。

<details>
<summary>Original English</summary>

**Host**: Okay. So, apparently I read way too much industry news, but now you're in charge of this.

</details>

**Amanda McMaster**: 是的。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yes.

</details>

**Host**: 它多次易手，而你们从本质上在人形机器人领域是独一无二的，变成了现在的众多公司之一。我们现在在巴黎的 Machina 峰会上，你看到了许多同行。那么，波士顿动力现在在做什么？它还是一个研究项目，还是说你们正在进入现实世界并应用这些机器人？因为我认为你们入局很早，但现在必须应对激烈的竞争。是的。

<details>
<summary>Original English</summary>

**Host**: It's changed hands many times and you went from being essentially one of one really in humanoid robotics to one of many. We're here at this Machina Summit in Paris and you see many contemporaries now. So, what is Boston Dynamics working on now? Is it still a research project or are you going into the real world and applying these robots? Because I think you guys got there early, but you have to now deal with fierce competition. Yeah.

</details>

**Amanda McMaster**: 是的，我们非常致力于机器人的部署。因此，它不再是一个人工智能实验室的实验项目。它也不再是一家纯研发公司了。我们现在专注于现实世界的部署。所以，我们从 Spot 机器人开始，很多人都知道它。那是我们的移动四足机器人，主要在工业领域……

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yeah, we are big on deploying robots. So, it's no longer an AI lab experiment. It's not a research and development company anymore. We're now focused on real world deployment. So, we started with our spot robot, which many people know. That's our mobile quadruped in industrial...

</details>

**Host**: 最著名的是在《黑镜》中追捕人类的机器狗，虽然那不是你们的。哦，不过你们完全可以承认那是指代你们的，对吧？总会有一个反乌托邦的版本和一个乌托邦的版本。你们显然在追求乌托邦，但那确实是一个非常酷的机器人，而且已经投入部署了。

<details>
<summary>Original English</summary>

**Host**: famously in Black Mirror chasing people down, not yours. Oh, you can own it, right? There's always going to be a dystopian version and a utopian version. You're obviously pursuing the utopian, but that is a really cool robot that has been deployed.

</details>

**Amanda McMaster**: 是的，它已经部署在真实的客户现场了。它正在提供真正的客户价值。到目前为止，我们在 46 个国家拥有 500 多家客户。哇。它是目前地球上使用量最大的移动自主机器人。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yes, it has been deployed in real customer sites. It's providing really customer value. At this point we have over 500 customers over 46 countries. Wow. It is the mobile autonomous robot that's used more than any other on the planet right now.

</details>

**Host**: 哇。所以它是部署最多、利用率最高的。

<details>
<summary>Original English</summary>

**Host**: Wow. So it is the most deployed and most utilized.

</details>

**Amanda McMaster**: 是的。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yes.

</details>

**Host**: 那么为什么呢？它排名第一的用例是什么？是安全防卫吗？还是巡检？人们使用那种机器狗形态是为了做什么？或者说机器小马。你喜欢叫它什么？小马狗？

<details>
<summary>Original English</summary>

**Host**: So real why and who's what is the number one use case for it? Like is it security? Is it inspections? What do people use that dog format for? Yes. Or pony. What do you like to call it? Pony dog.

</details>

**Amanda McMaster**: 我们倾向于把它看作是一只狗。我的意思是，我觉得它的动作很像狗。但是，你知道，客户在工业检测中发现了它的很多价值。所以，他们将它用于声学监测、仪表读数、振动检测。对于那些在设施中拥有昂贵资产并希望对其进行监控的客户，这使他们能够做到这一点。现在，它可以在白天做这些，然后在晚上进行周边安全巡查。所以答案是肯定的，我们所有这些都做。而且真正的拐点是客户的投资回报率（ROI），对吧？我们希望客户能在其中找到价值，去做真正有用的工作。这不再仅仅是因为它很可爱而且会跳舞，它早已经过了跳舞的阶段。它现在正在做真正的工作。而且客户需要在两年内看到他们的投资回报。

<details>
<summary>Original English</summary>

**Amanda McMaster**: We like to think of as a dog. I mean, I think it moves like that. But, you know, we're using this, the customers are finding a lot of value in industrial inspection. So, they're using it for both, you know, acoustic gauge reading, vibration detection. So, assets that, you know, if they have expensive assets in their facility and they want to monitor them, this allows for them to do that. Now, it can do that during the day and then it can do security perimeter work at night. Um, so the answer is yes, we do all of that. And the real inflection point was customer ROI, right? We want customers to find value in this to do really useful work. It's not just about yes, it's cute and it dances, but it's long past dancing at this point. It's now doing real work. And customers need to see your ROI in under two years.

</details>

**Host**: 而那些检查工作，如果以前有人做的话，也都是由人类来完成的。

<details>
<summary>Original English</summary>

**Host**: And those inspections, if they were even being done, were being done by humans.

</details>

**Amanda McMaster**: 是的。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yes.

</details>

**Host**: 我们都知道，人类是会犯错的。我们会犯错误。而这些机器人现在就像小狗一样在外面跑来跑去，在水处理设施、桥梁、或是任何基础设施和管道中工作。而且它可以记录许多不同的传感器数据：视频，显然还有振动、各种雷达——我猜的，以及你提到的各种声学数据。这些机器人的成本是多少？硬件成本的范围是多少？然后你们的商业模式是什么？人们是购买它们然后按小时租用大脑吗？作为首席执行官，你认为这些拥有数百台或数十台部署量的客户的商业模式是什么？

<details>
<summary>Original English</summary>

**Host**: humans, as we all know, being them are fallible. We make mistakes. And these ones were just out there now as little puppies running around a water treatment facility, a bridge, whatever it happens to be, infrastructure pipelines. And it can record many different sensors, video, obviously, vibrations, all radar, I'm assuming, all different tie acoustics you mentioned. What do those robots cost? What's the range of the hardware cost? And then what's your business model with these? People buy them and rent the brain. They rent it by the hour. What do you think of as the CEO will be the business model and what is the business model with these hundreds or dozens of customers deploying hundreds of these?

</details>

**Amanda McMaster**: 是的，对于 Spot，我们一开始采用的是资本支出（CapEx）模式。对于 Atlas，我们可能会采用机器人即服务（Robot-as-a-Service）的模式。我们理解，对于人形机器人这种形态，客户可能希望在不同的时间段启动它们，并有能力灵活增减。对于 Spot，资本支出模式一直相当有效。这也是这些工业客户思考工业工具的方式。因此，他们通常希望为此进行资本支出。这取决于他们的配置。基本款机器人的价格从 10 万美元起，如果加上服务、集成和部署，全配版的价格最高可达 30 万美元。就像从特斯拉到法拉利的价格，取决于你如何装备它。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yeah, so we went with a capex model to start with spot. We'll be doing a probably a robot as a service model likely with Atlas. We understand with the humanoid form factor folks may want to spin up at different times and then and have the ability to do decrease. With spot it's been pretty effective in capex. It's the way these industrial customers think about industrial tools. So they generally want to spend capex for this. It depends on their configuration. You know it ranges anywhere between you know $100,000 for the base robot all the way up to 300,000 fully loaded with services integration deploy. It's the price of a Tesla to a Ferrari depending on how you equip it.

</details>

**Host**: 但人们需要了解的是，我想这些机器人的使用寿命超过 5 年。比如，你们在工业界很有名。所以，如果它能运行，我假设算上充电，你每天可以运行 20 小时、22 小时。

<details>
<summary>Original English</summary>

**Host**: But what people need to understand is the lifespan of these is greater than 5 years I would think. Like these are you're known for industrial. So if it can run I'm assuming you can run 20 hours a day, 22 hours a day with charging.

</details>

**Amanda McMaster**: 是的。所以我们……我们通常用“平均无干预时间”（mean time between intervention）来衡量，我们已经超过了 3000 小时。所以一年中人类只需要介入几次。而且它有一个充电站。所以，电池大约可以运行 90 分钟。通常我们会配备两台，一台回来坐下充电，另一台就可以接管工作。

<details>
<summary>Original English</summary>

**Amanda McMaster**: Yep. So we're at um we think about in terms of mean time between intervention and we're at over 3,000 hours. So only a couple times a year does a human have to be involved and it has a charging station. So, battery runs for about 90 minutes. Um, usually we'd have two, comes back, sits down and charges, and the next one can take over.

</details>

<!-- chunk 6/9 -->

### 电池续航与自动化充电

**Interviewer**: 它会自动更换电池吗，还是……

<details>
<summary>Original English</summary>

**Interviewer**: Does it automatically swap the batteries or

</details>

**CEO**: 它只会直接坐到充电底座上充电。这非常完美。

<details>
<summary>Original English</summary>

**CEO**: It just sits down onto its charging part. Perfect.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah.

</details>

**CEO**: 不过，Atlas 确实有可更换的电池。

<details>
<summary>Original English</summary>

**CEO**: Uh, Atlas has swappable batteries, though.

</details>

**Interviewer**: 是的。但是这种热插拔是需要人类来操作的。

<details>
<summary>Original English</summary>

**Interviewer**: Yes. But that the hot swap is a human has to do it.

</details>

**CEO**: 不。Atlas 可以自己完成这项操作。

<details>
<summary>Original English</summary>

**CEO**: No. Uh, Atlas does it itself.

</details>

**Interviewer**: 哦，它可以自己换。

<details>
<summary>Original English</summary>

**Interviewer**: Oh, it does it.

</details>

**CEO**: 所以，Atlas 会有两块电池。它只需转动躯干，你就可以取下一块并换上另一块。它始终有一块备用电池。所以，电池续航并不是大问题。因此，对于人形机器人来说，它可以自己更换电池。显然，机器狗是直接充电的。所以实际来看，它们可以在现场工作将近 24 小时，或者是 18、20 小时。

<details>
<summary>Original English</summary>

**CEO**: So, Atlas will have two batteries. So, it turns it torso around and you replace one and put it with the other one. It always has a backup. So, battery life's not perfect. So, for the humanoid one, it can do it itself. Obviously, the dog gets charged. So, realistically, they could be in the field for close to 24 hours, maybe 18, 20.

</details>

### 劳动力替代与投资回报

**Interviewer**: 这样一来，运营成本就降到了一小时几美元。成本的这种大幅下降，是否改变了人们对它的应用场景的看法？因为我想，像工会工人去检查管道，如果把福利、养老金之类的全算进去，他们每小时的工资大概要 40、50、60 美元。那是非常昂贵的。

<details>
<summary>Original English</summary>

**Interviewer**: And so, that puts the operations at a couple of dollars an hour. And has that changed how people look at the use case, the dramatic lowering of cost, cuz I'm assuming union workers inspecting, you know, pipelines, they're getting paid 40, 50, 60 bucks an hour fully baked with their benefits, their pension, whatever else. it it's quite expensive.

</details>

**CEO**: 对于 Spot，我们并没有必然从劳动力替代的角度来看待它。虽然那可能是你关注的一个指标，但我们考虑的是，我们该如何引入 Spot 来辅助人类劳动力。首先，有些任务即便分配给了人类，他们也根本不会去做；其次，我们只是想找出一些方法，让人类能去完成更多，你知道的，更多知识型工作任务，而不是去跑去执行检查任务。所以没错，客户评估投资回报率（ROI）的指标之一可能确实会看劳动力替代的情况。不过我们现在更倾向于关注“我们能为你省下多少钱？”比如，我们在你们的设施里发现了一处漏气，如果没发现，那可能一度会导致每天损失 300 万美元。

<details>
<summary>Original English</summary>

**CEO**: We haven't necessarily looked at labor replacement for spot. Um while while that is a metric you might look at. We thought about you know how do we bring spots in there to augment human labor. One humans weren't doing the task even if they were tasked with it they weren't actually doing it. And two like we're just trying to figure out ways that humans can do more you know knowledge worker tasks as opposed to going and doing inspection. So yes one of the metrics a customer might look might look like for ROI is is labor replacement. We're leaning more into how much do we save you? So we found an air leak in your facility and that was a would have been $3 million a day at one time.

</details>

**Interviewer**: 是的。最终的结果才是关键。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. The outcomes matter.

</details>

**CEO**: 没错。那么我们在创造的价值究竟是什么呢？

<details>
<summary>Original English</summary>

**CEO**: Yes. So what is the value that we're driving?

</details>

**Interviewer**: 但是，现在在这个行业里谈论劳动力替代是不是依然很敏感？所以在这个特定的时期，你必须得非常谨慎地对待这个话题。

<details>
<summary>Original English</summary>

**Interviewer**: But it's is it still delicate in the industry to talk about labor replacement. So you have to be very thoughtful about that in this moment of time.

</details>

**CEO**: 咱们老实说吧。我的意思是，这其中肯定会有将劳动力替代作为一个衡量指标的成分在里面，因为这很容易算。你知道世界上有多少劳动力，由此你就能想象出与之相关的总体潜在市场。我只是认为，这不应该成为我们唯一讨论的话题，对吧？它仅仅只是其中一个因素而已。

<details>
<summary>Original English</summary>

**CEO**: And let's be honest. I mean there's going to be an element of labor replacement for this as a metric because it's easy. You know how many bodies are in the world and how can you imagine a total addressable market relative to that. I just don't think it's the only conversation we should be having, right? Just an element of it.

</details>

**Interviewer**: 而且希望我们能够消除那些危险的工作，以及那些人们可能会觉得压抑的工作。

<details>
<summary>Original English</summary>

**Interviewer**: And hopefully we're getting rid of the the dangerous jobs and the ones people might find um oppressive.

</details>

**CEO**: 是的。

<details>
<summary>Original English</summary>

**CEO**: Yeah.

</details>

**Interviewer**: 呃……就是那些枯燥、肮脏、危险的工作。

<details>
<summary>Original English</summary>

**Interviewer**: Uh dull, dirty, dirty, dangerous.

</details>

**CEO**: 枯燥、肮脏、危险。

<details>
<summary>Original English</summary>

**CEO**: Dull, dirty, dangerous.

</details>

**Interviewer**: 是的，我们不想让那些工作伤害到他们的身体。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. We don't want that hurting their body.

</details>

**CEO**: 对。人类的身体只有一副，这是不可替代的。

<details>
<summary>Original English</summary>

**CEO**: Yeah. We We only get one human body. Yeah.

</details>

### 机载计算与云端大脑

**Interviewer**: 呃，关于 Atlas，在赋予机器人多少大脑算力这个问题上，你是怎么权衡机载计算和远程计算的？据我理解，你们把大脑装在了机器人身上。

<details>
<summary>Original English</summary>

**Interviewer**: Uh the Atlas, how do you think about onboard compute versus remote when you put the amount of brains? Uh my understanding is you have the brains on the robot.

</details>

**CEO**: 是的。

<details>
<summary>Original English</summary>

**CEO**: Yep.

</details>

**Interviewer**: 那就意味着极其可怕的电池消耗。你觉得有没有一种可能，把所谓的“大脑”放到云端，让这些机器人本身变得更轻量化？前提是它们处于高速 Wi-Fi 覆盖的区域等环境中。你们现在有提供这样的选项吗，还是说全都是“嘿，你必须得买一个装有很多大脑算力的机器人，因为这就是客户想要的”？这似乎是当前正在发生的一种范式转变。

<details>
<summary>Original English</summary>

**Interviewer**: That means crazy battery drain. What do you think about the option of having, you know, the uh brains in the cloud and having these be more lightweight if they're in an area that has extremely high speed Wi-Fi, etc. And do you offer that yet or is it all, hey, you got to have a robot with a lot of brains on it cuz that's what the customers want. And that seems to be a paradigm shift that's occurring now.

</details>

**CEO**: 对。

<details>
<summary>Original English</summary>

**CEO**: Yeah.

</details>

**Interviewer**: 那么，你对此是如何理解的，或者我们该如何看待它？

<details>
<summary>Original English</summary>

**Interviewer**: So, how do you gro that or how should we think about it?

</details>

**CEO**: 我们将其理解为“两个大脑”，对吧？这是我讲这个故事的一个简化版本。有两个大脑。控制机器人物理动作的大脑，这正是波士顿动力公司（Boston Dynamics）所闻名的。比如动态运动、可靠性，以及它在现实世界中操作物体的方式，这些都驻留在机器人本体上。而其下方提供对环境进行语义理解的推理层，则可以部署在云端。这部分内容我们可能会与 Google DeepMind 合作，或者可能与其他 AR 合作伙伴合作，亦或是我们自己构建一部分；最后，包裹在所有这些之外的一层封装，就是特定客户围绕其自身工作流程所需的非常具体的信息。比如他们思考自身拥有的工作流程的方式、他们设施中现有的工具，以及这台机器人将如何与其进行交互。这一层将存在于两者之间的某个位置。所以，如果需要的话，它可以放在机器人端。它也可以放在云端。我们会弄清楚该如何去封装这部分。

<details>
<summary>Original English</summary>

**CEO**: We think about two brains, right? It's my simplified version of telling the stories. There's two brains. Okay. There's the the brain that controls the physicality of the robot, which is what Boston Dynamics is known for. Know the dynamic movement, reliability, the way it manipulates things in the world that lives on the robot. The reasoning layer that under that gives you the semantic understanding of its environment that can be in the cloud. That's things that we might partner with Google Deepine or we may partner with other AR partners or who will build some of this oursel and then the wrapper around all of that is the very specific information that a particular customer needs around their own workflows. You know the way that they think about the um the job processes that they have and the tools that exist in their facility and how this robot will interact with it. That's going to live somewhere in between. So it could be on on robot if you needed it to. It could be in the cloud. Um we'll figure out the wrapper for that.

</details>

### 国家安全与地缘政治竞争

**Interviewer**: 你们的机器人今天有多少百分比是在美国制造的，或者是中国和台湾以外的地方制造的？

<details>
<summary>Original English</summary>

**Interviewer**: What percentage of the robot is built in the United States or outside of China and Taiwan today?

</details>

**CEO**: 100% 的机器人。

<details>
<summary>Original English</summary>

**CEO**: 100% of the robots.

</details>

**Interviewer**: 100%。所以在美国，机器人的主权没有问题。但我们现在看到许多廉价机器人从中国涌现出来。

<details>
<summary>Original English</summary>

**Interviewer**: 100%. So there's no issue with the sovereignty of robots in the United States. We're seeing a lot of cheap robots coming out of China.

</details>

**CEO**: 是的。

<details>
<summary>Original English</summary>

**CEO**: Yeah.

</details>

**Interviewer**: 作为这家公司的 CEO，同时也作为一名美国人，你个人的观点是，无论在任何情况下，我们是否应该允许来自中国的人形机器人进入美国？

<details>
<summary>Original English</summary>

**Interviewer**: Your personal opinion as the CEO of this company and as an American, under any circumstances, should we allow humanoid robotics from China in the United States?

</details>

**CEO**: 不应该。

<details>
<summary>Original English</summary>

**CEO**: No.

</details>

**Interviewer**: 不应该。为什么？

<details>
<summary>Original English</summary>

**Interviewer**: No. Why?

</details>

**CEO**: 因为这不安全。对吧。我们已经听说过一些消息，关于你们在美国看到的某些四足机器人的数据正在被秘密传回中国。听着，我们已经见识过，如果我们让中国在半导体领域获胜会发生什么。我们绝不能在机器人领域重蹈覆辙。因此，我们需要齐心协力地去保护我们的知识产权，去确保我们将这一生态系统的制造业带回美国，或是我们的盟国。这意味着我们需要把机器人上升到国家战略的高度。很幸运，我们能在其中的一些讨论中获得一席之地。我希望美国有更多的公司能够加入我们，共同承担起这项使命。

<details>
<summary>Original English</summary>

**CEO**: It's not safe. Right. We've already we've already heard um about leaks that are happening with some of the quadripeds that you're seeing um in the United States and it's being back channelled back to China. Listen, we we have seen what happens if we let China win in the semiconductor space. You know, we can't do that with robotics. So, we need to have a concerted effort to protect our IP to um make sure that we are bringing manufacturing of of this ecosystem into the United States or into our allied countries. And that means that we need to take our national robotic strategy. We're lucky enough that we get to sit at the table in some of these discussions. Um I'm hoping that more companies in the US join us um in in taking taking up this mission.

</details>

**Interviewer**: 是的，我们必须对此非常严肃。这是一个关乎存亡的问题，因为这……不仅我们必须赢得这场竞争，我们还必须确保世界其他国家使用的是我们的平台，而不是中国的。你是如何看待这些机器人的军事应用的？显然，军事领域已经因为无人机而发生了改变，这种改变的方式和速度——不是故意一语双关——我认为这是任何人都始料未及的，看看在乌克兰发生的事情，以及现在我们在中东看到的与伊朗的战争就知道了。你是怎么看待 Atlas 和 Spot 在战场上的应用的？目前它们在军队中的部署情况如何？

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, we have to be pretty serious about this. It's an existential issue because these not only do we have to win this, we have to make sure that the rest of the world uses our platform rather than China's. How do you think about the military application of these? Obviously military is uh you know the the the field has been changed with drones in a way and at a velocity no pun intended that I don't think anybody anticipated because of what's happened in Ukraine and now we see in the Middle East with the war with Iran. How do you think about Atlas and Spot in the battlefield? Where are they at in terms of deployment uh in the military?

</details>

**CEO**: 是的。所以，我们一直以来都在非常公开地表达我们的立场，那就是我们反对武器化。但是听我说，我认为，就我们目前试图在工业用例中去实现的目标而言，这（军事化）对我们的业务是一种干扰，你懂的。

<details>
<summary>Original English</summary>

**CEO**: Yeah. So, we've been we've been pretty public about the fact that we have an anti-weaponization stance. Um but listen, um I think that um for what we're trying to do right now um in industrial use cases, it's a distraction for our business, you know.

</details>

**Interviewer**: 所以，重点在于专注。

<details>
<summary>Original English</summary>

**Interviewer**: So, focus.

</details>

**CEO**: 没错，就是专注。

<details>
<summary>Original English</summary>

**CEO**: It's focused.

</details>

**Interviewer**: 这不是什么哲学问题。

<details>
<summary>Original English</summary>

**Interviewer**: It's not philosophical.

</details>

**CEO**: 它是……我的意思是，这取决于你去问公司里的谁。作为 CEO（也可能是 CFO），看待这个问题时我会说，我现在满脑子想的都是保持专注。我们需要专注于那些我们认为能够取胜的市场。当然，我们与政府保持着良好的关系，我们也很乐意与他们开展任何非武器化的合作。而且，我们今天确实也在这样做。

<details>
<summary>Original English</summary>

**CEO**: It's I mean, it depends on who you ask in there. As the CFO CEO, you know, I'm going to look at this and say I'm all about focus right now. We need to be focused on the markets that we think we're going to win in. Um, and certainly we have great ties with the government and we're happy to do any non-weaponization work with them. Um, and we do do that today.

</details>

**Interviewer**: 好的。也就是说，你们会将它们或者说已经将它们部署在战场上了。如果必须让它去接走一名士兵，或者运送一个医疗包，你会觉得没问题。拆除炸弹，你觉得也没问题。

<details>
<summary>Original English</summary>

**Interviewer**: Okay. So, you'll have them in or you do have them in the field. Maybe if it had to go collect a soldier or bring a med pack, you'd be okay with that. Disarming a bomb, you're okay with that.

</details>

**CEO**: 爆炸物处理（EOD），排爆是……这是机器人非常棒的一个应用场景。

<details>
<summary>Original English</summary>

**CEO**: EOD, we EOD is one of, you know, explosive ordinance disposal is something that's a great use case for robots.

</details>

**Interviewer**: 而且你们目前也正在这样做。

<details>
<summary>Original English</summary>

**Interviewer**: And you're doing that currently.

</details>

**CEO**: 我们目前正在这样做。所以，我们对此没有异议。但我们不想要的是“终结者”那样的机器人，对吧？

<details>
<summary>Original English</summary>

**CEO**: We do that currently. So, we're okay with that. Um, what we don't want is Terminator robots, right? It's

</details>

**Interviewer**: 这对市场不好，但是中国正在制造它们。所以如果中国在制造它们而我们不造，对吧？如果你是波士顿动力，你在某种程度上是有义务去制造它们的。所以如果中国把这些投入到战场，你们会为了保卫美国而去制造它们吗？

<details>
<summary>Original English</summary>

**Interviewer**: not good for the market, but China's building them. So if China's building them and we don't, right? You're kind of obligated if you're Boston Dynamics to build them. So if China puts these into the field, will you build them to protect America?

</details>

**CEO**: 我觉得这是个很棘手的问题，我想当那一刻真正来临的时候，我们将不得不给出答案，不过希望那一天永远不会到来。

<details>
<summary>Original English</summary>

**CEO**: I think that's a tough that's a tough question and I think we're going to have to answer it when the time comes and hopefully it never comes.

</details>

**Interviewer**: 那一天肯定会到来的，我可以向你保证。而且我也可以向你保证，当特朗普总统打来电话时你的回答将会是什么。你会说，“是的，长官。”否则你的公司就会被国有化。我的意思是，这就是现实。我当然是在跟你开玩笑，稍微有点戏谑。但是他们一定会部署这些机器人的，而且他们已经展示过了。你看到过他们在这些机器人上装备 AK-47 吧。

<details>
<summary>Original English</summary>

**Interviewer**: The time is going to come. I can assure you. And I can assure you what your answer will be when President Trump calls. You will say, "Sir, yes, sir." or else your company will be nationalized. I mean, this is the reality of it. I mean, I'm being a little facicious and playful with you. But they're going to deploy these and they're going to deploy them and they already have shown. You've seen them put AK-47s on these.

</details>

**CEO**: 是的。但不是在我们的机器人上。

<details>
<summary>Original English</summary>

**CEO**: Yes. Not on our robots.

</details>

**Interviewer**: 不是在你们的，是在他们的机器人上。

<details>
<summary>Original English</summary>

**Interviewer**: Not on yours, on theirs.

</details>

**CEO**: 对。而且听着，那太可怕了。非常可怕。

<details>
<summary>Original English</summary>

**CEO**: Yes. And on And listen, it's terrifying. Terrifying.

</details>

**Interviewer**: 我想，听着，我知道我们拥有世界上最好、最能干的机器人。你明白，如果那一天真的到来，我们……

<details>
<summary>Original English</summary>

**Interviewer**: I think, listen, I know that we have the best robot and the most capable robot in the world. You know, if and when that time came that we

</details>

<!-- chunk 7/9 -->

### 告别波士顿动力临时 CEO

**Interim CEO of Boston Dynamics**: ……如果我们不得不做出艰难的决定，我们会做出正确的选择。嗯，但今天我们不必做那个决定。所以，我将让每个人都专注于那些对我们来说能合理盈利的应用领域。而且……

<details>
<summary>Original English</summary>

**Interim CEO of Boston Dynamics**: ... had to make a tough decision, we would make the right one. Um, but today we don't have to make that decision. So, I'm going to keep everyone focused on the application space that makes a lot of sense for us to make money. And

</details>

**Host**: 我要告诉你一个秘密。别告诉任何人。中央情报局（CIA）、联邦调查局（FBI）和战争部目前有很多你们的机器人，上面安装了许多武器。别告诉任何人。好吧，听着，我知道你得走了。祝你继续取得成功。这是一家非常重要的美国公司，而且，呃，我希望你能接受这份工作并成为全职 CEO。我知道你现在是临时的。现在还是临时的。呃，所以，我祝你好运。如果有人想来波士顿动力（Boston Dynamics）工作，请告诉大家你们的总部在哪里？

<details>
<summary>Original English</summary>

**Host**: I'm going to tell you a secret. Don't tell anybody. The CIA, the FBI, and the Department of War have many of your robots with many weapons attached to them currently. Don't tell anybody. All right. Listen, I know you got to go. Continued success. This is such an important American company and uh I hope you take the job and become full-time. I know you're interim right now. Interim right now. Uh so I I wish you great luck with it. If people want to come work at Boston Dynamics, please tell where are you based?

</details>

**Interim CEO of Boston Dynamics**: 嗯，我们在沃尔瑟姆（Waltham），就在波士顿郊外。嗯，但我们对一些远程工作持开放态度，而且，嗯，我们正在考虑来到西海岸。所以……

<details>
<summary>Original English</summary>

**Interim CEO of Boston Dynamics**: Um so we're in Waltham, so right outside of Boston. Um but we're open to some remote work and um we're considering coming to the West Coast. So

</details>

**Host**: 我正想说，你知道，我的意思是，我知道波士顿动力这个名字里有“波士顿”，但我认为随着那么多人才聚集在湾区，你们将需要在那里设立一个办公空间。是的。

<details>
<summary>Original English</summary>

**Host**: I was about to say, you know, I mean, I know it's in the name Boston Dynamics, but I assume with all that talent accumulating in the Bay Area, you're going to need to pop up a a space there. Yeah.

</details>

**Interim CEO of Boston Dynamics**: 是的，我们步调一致。

<details>
<summary>Original English</summary>

**Interim CEO of Boston Dynamics**: Yeah, we're consistent.

</details>

### 对话 Agility Robotics 首席机器人官 Jonathan Hurst

**Host**: 好吧。听着，祝你继续取得成功。非常感谢。好了，各位。我们的下一位嘉宾是 Jonathan Hurst 教授。他是 Agility Robotics 的联合创始人兼首席机器人官。你在2008年获得了机器人学博士学位。

<details>
<summary>Original English</summary>

**Host**: All right. Listen, continued success. Thank you so much. All right, everybody. Our next guest is Professor Jonathan Hurst. He's the co-founder and chief robotic officer or chief robot officer at Agility Robotics. You have a PhD in robotics from 2008.

</details>

**Jonathan Hurst**: 是的。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: Yeah.

</details>

**Host**: 所以，你在这个领域已经深耕了20多年。

<details>
<summary>Original English</summary>

**Host**: So, you've been at this for over 20 years.

</details>

**Jonathan Hurst**: 远超20年了。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: Well over 20 years.

</details>

**Host**: 在过去的36个月里，事情似乎已经升温了。也许在讨论你们的产品线之前，你可以为观众们设定一个基准，谈谈你在过去20年里看到了什么。过去两年的发展与之前的20年相比又是怎样的？

<details>
<summary>Original English</summary>

**Host**: Things seem to have heated up in the last 36 months. Maybe you could for the audience at before we get into your product line level set what you've seen in the past 20 years. Yeah. And how the last two years compares to the previous 20.

</details>

**Jonathan Hurst**: 是的。我的意思是，20年前当我们做这件事的时候，它确实是一个未知的行业，对吧？机器人技术当时更多是关于自动化系统的。而在研究界，我们在做像人形机器人、自主移动机器人等事情，呃，真正试图构建智能，然后构建能够使其具备能力的硬件设施，嗯，这现在确实已经开始突破进入现实世界，产生了超出作为一个研究课题之外的直接影响。而且大学里也看到了这种需求和增长，人们喜欢机器人，很多学生有学习这个的需求。因此，相关项目的数量增加了，并且呈指数级增长，非常非常令人兴奋，非常令人兴奋。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: Yeah. I mean 20 years ago when we were doing this, it really was an unknown industry, right? Robotics was more about automation systems. Yeah. And in the research community, we're doing things like humanoid robots, like autonomous, you know, mobile robots. uh really trying to build the intelligence and then build the hardware that can cap be make it capable um and that's really started to break through now into the real world into having direct impact beyond being a research topic and then the universities have seen this demand and this growth and people love robots there's a lot of demand from students who want to do it so the number of programs has grown and it's just exponentially growing very very exciting very exciting

</details>

**Host**: 在你所专攻的人形机器人和人工智能领域，我们经历过很多次失败的尝试。人们称之为“人工智能寒冬”，你知道的，有好几次这样的低谷。但这一次显然是来真的了。请向观众解释一下为什么这次不同，为什么你相信这一次我们将看到机器人，特别是人形机器人，能够大规模部署。我想我们都会同意，也许在未来20到30年内，地球上的机器人数量将与人类数量达到一对一的比例。这非常有影响力。那么，为什么这次会有所不同呢？

<details>
<summary>Original English</summary>

**Host**: we've had a lot of false starts with humanoid robot which you're specializing in and AI and AI. They call it the AI winters, you know, human multiple ones. This time is real quite obviously. explain to the audience why this time is different and why you believe this time we're going to see robotics and humanoid robotics specifically deployed at a scale that I think we can both agree will be maybe in the next 20 30 years onetoone with humans on the planet very impactful yeah why why is this time different

</details>

**Jonathan Hurst**: 是的，嗯，我大致会说，制造一个看起来像人的机器人是非常容易的，这就是为什么我们在过去一百年里已经看到了人形机器人的原因。但要制造一个能在人类空间中做有用事情的机器人，是非常困难的。我们今天开始看到这种情况了，这就是区别所在。所以，即使它看起来不完全像人，可能只是一点点像人，但它在做有用的工作，那才是影响力所在。而且由于大型语言模型，现在很多事情已经变得免费了。当这些机器人看着这里的桌子，你说：“桌子上有什么？”它知道那是一部手机。它知道这是纸、茶、水。它可能还知道每种东西有多少盎司。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: yeah well I would say generally it is very easy to make a robot that looks like a person and that's why we've seen humanoid for 100 years in one. It's very hard to make a robot that can do useful things in human spaces. And we're starting to see that today and that's the difference. So even if it doesn't look exactly like a human, but maybe a little bit humanoid, but it's doing useful work, that's where the impact matters. And because of large language models, a lot of things have now become free. When these robots look at a table here, Yeah. and you say, "What's on the table?" It knows that's a phone. It knows this is paper, tea, water. It probably knows how many ounces are in each.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Jonathan Hurst**: 如果它是三四年前坐在这里，它实际上不会知道世界上有什么。你必须以一种非常狭隘的方式对其进行编程。是的。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: If it were sitting here 3 or 4 years ago, it wouldn't actually know what was in the world. You would have to program it in a very narrow way. Yeah.

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Jonathan Hurst**: 感知曾经非常困难。而现在感知问题几乎已经被解决了，这确实是一个非常、非常巨大的拐点。我的意思是，你知道，我说过，是的，机器人在做有用的事情，但人们现在也能看到通用性的未来。人工智能确实在很大程度上使这些机器人具备了更广泛的上下文感知能力，所以人们可以看出，这很快将在一般情况下发挥作用，去做许多有用的事情。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: Perception was incredibly difficult. And the fact that perception is all but solved at this point is a really, really huge inflection point. I mean, you know, I said, yes, robots doing useful things, but also people can now see the future of generality. AI is really enabling that much more broad um you know context awareness for these robots so people can see that this is going to be useful gen generally doing many useful things very soon.

</details>

**Host**: 所以，机器人必须拥有去理解世界的感知能力。

<details>
<summary>Original English</summary>

**Host**: So there's perception the robot has to understand the world.

</details>

**Jonathan Hurst**: 对。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: Yep.

</details>

**Host**: 但在那之后，要让机器人摆脱在一个非常封闭、狭窄的任务中（比如在工厂里），似乎总存在一个障碍。我的感觉是，这个障碍在于交流和训练水平。也许我们可以稍微剖析一下这一点，因为我的理解是，以前如果你想让机器人煮一杯咖啡，你基本上必须对机器人进行硬编码。我投资了一家名为 Cafe X 的公司，它是一个机械臂，每次都能完美地煮出一杯咖啡，能打生啤等等，但它必须是手动编码的。而现在，指令集因为感知能力，因为语言模型，已经在互联网上的每个视频、每个似乎也是免费的咖啡配方上进行了训练。我说的有错吗，或者现在还没到那一步？

<details>
<summary>Original English</summary>

**Host**: But then there always seemed to be this blocker with getting the robot out of a very confined narrow task like you know in a factory and I my perception is it was the communication and the training level. Maybe we can unpack that a bit because my understanding was previously you basically had to hardcode the robot if you were going to make a cup of coffee. We have a company I invested in Cafe X and it is a robotic arm. Mhm. makes a cup of coffee perfectly every time, can draft a beer, all that stuff, but it had to be manually coded. Now, the instruction set because of perception, because of language models, having trained on every video on the internet, every coffee recipe that also seems to be for free. Am I wrong or not yet?

</details>

**Jonathan Hurst**: 实际上情况完全不同。语言模型，你可以认为它现在正在成为一种像互联网一样的商品。每个人都可以使用它。这是一股惊人的浪潮。但这些语言模型是基于互联网上的所有数据进行训练的，而这种数据并不存在于机器人控制中。你知道，给你所有传感器的输入后，要给每个电机下达的所有扭矩命令是什么？并没有这样的训练数据集。所以你必须以某种方式生成和创造这些数据。对于这一点，人们正在采取许多不同的方法和途径。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: It's actually quite different. So, language models, think of it like it's a it's now becoming kind of a commodity like the internet. It's available to everybody. It's this amazing rising tide. But these language models are trained off of the entire data on the internet and that data does not exist for robot control. You know what's the example for your robot of all the torqus all the torque commands to every motor given all the sensor input. There's no training set of data. So you have to generate and create that somehow and there's a lot of different approaches and ways people are are going about this.

</details>

**Jonathan Hurst**: 再次强调，不要把人工智能仅仅看作是一个黑匣子，而是把它看作是涵盖了许多极其不同但都有用的计算工具的大帐篷。为了控制机器人，你可以通过从演示中学习来做到这些。你可以远程操作机器人，从这些数据中开始训练；嗯，你可以给它输入动画数据或者动作捕捉数据，或者其他很多不同的东西。但那也有一个真正的硬性限制，因为一个控制机器人的人，并没有真正达到如果优化的话机器人本身能做什么的水平，以及机器人的行为可以如何运作。机器人的那个部分是需要练习的。所以这就涉及到世界模型和“从模拟到现实（sim-to-real）”的迁移，以及所有这一类事情。而世界模型是下一个前沿。人们现在真的戴着手套，呃，远程控制机器人，去实际切菜、做沙拉、倒水，现在有很多不同的公司都在做这件事。世界模型将解决这个问题。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: And some of these AI tools again think of AI not as a blackbox but as a big tent of many different very different useful computational tools right in order to control a robot you can do these things by learning from demonstration you can give it you can tellyoperate the robot start to train from that data um you can give it animation input or motion capture input or any number of different things but that's also got a real hard limit because a person controlling a robot is not really getting to what the robot can do if if it were optimal and how its behavior could work that of a robot needs to practice you And that's where you get into world models and sim to real transfer and all of these kinds of things. And world models are the next frontier. People are literally putting gloves on humans uh and having them control robots remotely to actually chop and make a salad to pour water and that's being done today by many different companies. the the world models will solve this problem

</details>

**Host**: 或者它们是解决方案的一部分。

<details>
<summary>Original English</summary>

**Host**: or they are part of the part of the solution.

</details>

**Jonathan Hurst**: 就像所有这些事情一样，没有包治百病的灵丹妙药，对吧？

<details>
<summary>Original English</summary>

**Jonathan Hurst**: As with all of these things, there is no silver bullet, right?

</details>

**Host**: 所以据我理解，世界模型就是，你知道，你能不能模拟整个仓库，以及里面所有物体的所有物理特性，这样，这些机器人的模拟就可以在世界模型中去练习，而不会在现实世界中弄坏东西，并且你知道，通过压缩，你可以在几天内完成数百万次迭代计算之类的事情。但两者之间总会存在一个巨大的“从模拟到现实”的差距。事物的模拟并不完美。然后你知道，当你在现实世界中拿起某样东西时，会有波的动态变化，玻璃杯上会有冷凝水，而且机器人的动力学也无法被完美模拟。所有这些事情仍然非常、非常困难。这就需要在现实生活中用机器人进行真正的练习，才能……

<details>
<summary>Original English</summary>

**Host**: So the world models, as I understand it, are, you know, can you model an entire warehouse and all of the physics of all of the objects inside of it so that then simulations of these robots can go practice in the world model without breaking things in the real world and you know compress so you can do, you know, a million iterations within days and computationally and things like that. But there's always a massive simto toreal gap. Things aren't simulated perfectly. And then you know as you pick up something in the real world and the there's wave dynamics and there's condensation on the glass and the dynamics of the robot are not perfectly modeled. All these things are still very very difficult. That takes real practice in real life with robots in order to

</details>

**Jonathan Hurst**: 是的。

<details>
<summary>Original English</summary>

**Jonathan Hurst**: Yeah.

</details>

**Host**: 那么，会不会有一个奇点或交叉点，在那里通过递归学习，就像把机器人放在厨房里，让它自己犯错，然后说“做下一个测试，做下一个测试”，这也是我们教它如何下国际象棋或围棋的方法。我们没有告诉它“这是如何王车易位”。我们只是暴力破解，对它说尝试每一种计算，它就能够弄明白。现在有了这些递归循环，什么能让我们更快到达那一步？有人建立了一个世界模型，说开始递归吧，把机器人放进厨房，然后你知道，弄坏很多……

<details>
<summary>Original English</summary>

**Host**: So, is there going to be a singularity or a crossing over moment where recursive learning, just putting the robot in the kitchen, Yeah. letting it make its own mistakes and then saying do the next test, do the next test, which is how we taught it how to win at chess or go. We didn't tell it like here's how to castle. We just brute force it and said try every computation and it was able to figure it out. Now with these recursive loops, what will get us there quicker? Somebody builds a world model, says go get recursive, puts the robots into a kitchen, and you know, breaks a lot of

</details>

<!-- chunk 8/9 -->

### 机器人技术的发展：滚雪球式的进步

**Interviewer**: 中国。还是说，这些世界级的模型公司将会非常精细地让机器人在米其林星级厨房里与人类并肩工作，你知道的，去制作那道舒芙蕾。

<details>
<summary>Original English</summary>

**Interviewer**: China. Or is it going to be these world model companies very refinedly working human alongside robot in a Michelin starred, you know, kitchen to to make that sule.

</details>

**Jonathan**: 我的意思是，这可能不是一个非常令人满意的答案，但这涉及所有的工具。是所有的，对吧？这里根本不存在什么万能灵药（silver bullet）。我不相信存在所谓的“奇点”。但我确实相信事情会变得越来越好。你可以把它更多地想象成一个雪球，在滚下山的过程中不断积蓄力量。明白吗？

<details>
<summary>Original English</summary>

**Jonathan**: I mean, that's it's not a very satisfying answer maybe, but it's all of the tools. all of them, right? There's not um a silver bullet at all here. I don't believe that there's this singularity. I do believe that things are going to get better and better. Think of it more like a snowball picking up steam going down a hill. Got it?

</details>

**Interviewer**: 但是，它之所以能像这样滚雪球般发展，是因为人们在探索这一切并开始弄清楚所有这些东西的过程中，投入了大量的资金、资源、工程时间以及工程努力。

<details>
<summary>Original English</summary>

**Interviewer**: But the reason that it's snowballing like this is because people are putting money and resources and engineering time and engineering effort in as they explore everything and start to figure all of this stuff out.

</details>

**Jonathan**: 没错。那么，以人类为例，我们是进化来学习的。我们非常擅长学习，只需要很少的数据就能向我们展示如何去做某件事。然后我们就会不断练习、实践并迭代。机器人目前在学习方面还不是很好。与人相比，机器人需要更多的数据、更多的例子。我们仍在弄清楚如何教机器人去学习。但是，从长远来看，机器人拥有的一个优势是它们有 Wi-Fi。你知道，当你学习如何拉小提琴时，你不能只是把这些知识下载给另一个人，然后他们就能根据你的学习成果知道怎么拉小提琴。而机器人将能够做到……

<details>
<summary>Original English</summary>

**Jonathan**: All right. So, but humans, for example, we've evolved to learn. We are very good at learning and it takes very little data to show us how to do something. And then we practice and practice and iterate. Robots are not very good at learning yet. Robots take so much more data, so many more examples than a person. We're still figuring out how to teach robots how to learn. Um, but then one of the benefits that robots have in the long run is they've got Wi-Fi. You know, when you learn how to play the violin, you can't just load that to somebody else and then they learn how to play the vi know how to play the violin based on your learnings. Robots will be

</details>

**Interviewer**: 一个机器人学会了拉小提琴。所有的机器人都知道怎么拉小提琴了。

<details>
<summary>Original English</summary>

**Interviewer**: one robot learns to play violin. All robots know how to play violin

</details>

**Jonathan**: 或者说那种类型的所有机器人就都知道如何拉小提琴了。对的。是的。

<details>
<summary>Original English</summary>

**Jonathan**: or all robots of that type know how to play the violin. Right. Yes.

</details>

### Digit 机器人的部署与安全性突破

**Interviewer**: 然后在下一代型号和下一件硬件设备上只需进行微小的调整。所以你们实际上正在部署你们名为 Digit 的产品。我想 Digit 现在是 4.0 版本。你们即将发布 5.0 版本。在现实世界中，你们已经有几十台设备应用在不同的场景中了。请给我们介绍一下如今的前沿部署是什么样的，以及你认为一两年后会发展到什么程度。

<details>
<summary>Original English</summary>

**Interviewer**: And then minor variations for the next type and the next piece of hardware. So you are actually deploying your product is called Digit. Digit is I think 4.0. You're going to release 5.0. You've got let's say dozens uh in different applications out there in the real world. Give us an idea of what the forward deploy looks like today and where you think it will be in a year or two.

</details>

**Jonathan**: 所以，今天它正在执行的这类多用途工作流程，范围仍然被框定得比较明确，比如捡起储物箱和手提箱并搬运它们。我们之所以这样做，是因为你需要两只手臂才能捡起大件物品。你需要全身的控制来灵巧地操作和移动它们。你需要保持平衡，以便在狭窄的空间里将它们举到高高的架子顶部。因此，这在某种程度上证明了这种外形设计在这个特定用例中的合理性。但是人形机器人真正有用的方面在于它的多功能性。因此，当我们进行拣选，你知道，装满一个箱子并把它搬到某个地方，以及码垛和卸垛，并扩展到越来越多的用例时，才是它真正开始爆发的时候。今年晚些时候即将推出的 Digit V5，将是人形机器人（一种能够保持平衡的机器人）首次能够走出工作单元，并且不需要在机器人和人之间设置物理屏障来维持仓库里的安全。所以当 Digit V5 推出时，这对我们来说算是一个规模化扩展的时刻。

<details>
<summary>Original English</summary>

**Jonathan**: So today it's doing these sort of multi-purpose workflows that are still reasonably well scoped like picking up bins and totes and carrying them around. And the reason we do that is because you need two arms to pick up big things. You need this whole body control to be dextrous in how you're manipulating and moving those. You need to be balancing to lift them to top of a tall shelf in narrow space. So it kind of justifies the form factor for this one use case. But the real useful aspect of a humanoid is its versatility. So when we do the each picking and you know fill a bin and carry it somewhere and palletizing and depalitizing and are expanding out into more and more use cases is when it really starts to escalate. And Digit V5 which is coming out later this year is the first time that a humanoid robot a robot which is balancing can step out of a work cell and does not need a physical barrier between the robot and the person to maintain safety in this warehouse. So when Digit V5 is out there that's kind of the scaling moment for us.

</details>

**Interviewer**: 是的，这是一个关键时刻，也许人们还没有意识到，但如果你去过埃隆（马斯克）的工厂或丰田的工厂，那里都有警戒线。那里划着一条线，如果你越过那条线……一切都会停转。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah, this is a key moment that maybe people don't appreciate, but if you've ever been to one of Elon's factories or Toyota's factories, there are lines. There's a line and if you cross that line, the everything shuts down.

</details>

**Jonathan**: 一切都会停转。

<details>
<summary>Original English</summary>

**Jonathan**: Everything shuts down.

</details>

**Interviewer**: 我曾和埃隆一起参观过很多次这样的工厂，他们会说：“说真的，请千万不要越过那条线，因为在特斯拉工厂，如果你越界了，就会损失一百万美元，因为工厂正在高速运转。”

<details>
<summary>Original English</summary>

**Interviewer**: And I I've taken many of these tours with Elon and they're like, "Seriously, please don't cross that line cuz it's going to cost a million dollars if you do at the Tesla factory cuz it's it's cranking.

</details>

**Jonathan**: 我们开始感到足够放心，这些机器人不会摔倒并弄断别人的脚踝。嗯，在过去的两三年里，这是一个非常、非常刻意的过程，对吧？当我们在亚马逊部署时，我们的经验是，机器人在执行任务，他们觉得太棒了，你知道，它实现了我们所有的研发目标，然后我们说，太好了，让我们去全面部署吧。但他们却说，哦不行，不行，我们不能部署，因为，你知道，它们不符合我们的安全要求。这就好比，好吧，我们该如何满足这个要求？事实证明这极其困难。因此，对这台机器进行的是自下而上的全新设计。从整体上看，机器人的每一个系统都经过了改造，以弄清楚如何让它变得安全。

<details>
<summary>Original English</summary>

**Jonathan**: We're starting to feel comfortable enough that these robots are not going to fall over and break somebody's ankle. Well, it's been a very very intentional process over the past 2 or 3 years, right? Where you know, this is our experience with Amazon when we deployed and the robots are doing the task and they're like great, you know, it it solves all the R&D uh, you know, goals we had and we're like, great, let's go deploy. And they're like, oh no, no, we can't deploy um because, you know, they they they're not they don't they don't meet our safety requirements. It's like, okay, how do we meet that? Well, it turns out that's super hard. And so, it's been a bottom to top design of this machine. Holistically, the whole every system of the robot is touched to figure out how to make it safe.

</details>

### 机器人的经济价值与商业模式

**Interviewer**: 当我们看一个像你们这样的工业缩小版机器人时，看看它的物料清单……

<details>
<summary>Original English</summary>

**Interviewer**: When we look at an industrial shrank robot like yours, bill of materials,

</details>

**Jonathan**: 嗯哼。

<details>
<summary>Original English</summary>

**Jonathan**: uh-huh.

</details>

**Interviewer**: 每台都要几万美元。对吧。

<details>
<summary>Original English</summary>

**Interviewer**: Tens of thousands of dollars each. Yeah.

</details>

**Jonathan**: 我的意思是，我们不是在讨论物料清单。我们知道，随着时间的推移，成本会不断下降。我们将会在汽车成本或类似价格区间内销售机器人。嗯，真正的问题是，它们产生的价值到底是什么，这是一个需要问的问题，当你有一台每天工作 24 小时、寿命长达 5 年的机器人时，你知道它的价值是什么，那是非常大的。

<details>
<summary>Original English</summary>

**Jonathan**: I mean, we're not discussing bills of materials. We know that the costs are coming down and down and down over time. We'll be selling robots, you know, in the vicinity of costs of cars and things like that. um the the real like what is the value that they produce is the question to ask when you have a robot that's working 24 hours a day and has a 5year life you know what's the value and it's quite a lot

</details>

**Interviewer**: 是的，如果我们从第一性原理来考虑的话，它们可以合理地每天运行 20 到 22 小时，然后它们必须充电，然后仅仅是……

<details>
<summary>Original English</summary>

**Interviewer**: yeah it would be uh if we were to think about it from first principles they can reasonably run 20 22 hours a day and then they have to charge and just

</details>

**Jonathan**: 没错。所以我们算每天 20 个小时。顺便说一句，一年 300 天，对于我们的 Digit V5 机器人来说，一天 24 小时中可以有 20 小时在工作状态，这是因为电池采用了非常快速的充电技术。

<details>
<summary>Original English</summary>

**Jonathan**: that's right be so we take 20 hours a day 300 by the way 20 out of 24 hours for our digit V5 robot on because of the very fast charge it generation that's gone in this battery.

</details>

**Interviewer**: 是的。所以我们有一年 365 天，每天 20 个小时，你知道，现在你已经达到了一年将近 7,8000 个小时。让我们算作一年 8,000 个小时，5 年就是 40,000 个小时的工作量。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. So we get we have 20 hours 365 days a year, you know, now you're in that 78,000 hours a year. Let's put it at 8,000 5 years 40,000 hours of work.

</details>

**Jonathan**: 这确实加起来很多。

<details>
<summary>Original English</summary>

**Jonathan**: It adds up.

</details>

**Interviewer**: 是的。人们往往认为这些东西会花费 20,000、30,000 甚至 40,000 美元。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. And people tend to think these things are going to cost 20, 30, $40,000.

</details>

**Jonathan**: 在某个时候它们确实会的。

<details>
<summary>Original English</summary>

**Jonathan**: They will at some point.

</details>

**Interviewer**: 是的。它需要经历规模化量产，并且在有十万台机器人投入使用之前，这才能成为现实。所以那大约是每小时 1 美元。目前这些工厂里工人的工资是每小时 40 美元。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. It's going to need to go through the scaling and have 100,000 robots out there before that actually is real. So that's a dollar an hour. These people are being paid in factories currently $40 an hour.

</details>

**Jonathan**: 是的。

<details>
<summary>Original English</summary>

**Jonathan**: Yeah.

</details>

**Interviewer**: 也许在其他一些国家是每小时 10 美元，但假设我们把它定在每小时 20 美元。当这些东西进入市场时，在某个时候你的成本就会有 90% 的压缩空间，这给了你足够的余地，可以按小时向亚马逊或丰田以及其他合作伙伴收费。目前计划是按使用小时收费吗？你们拥有机器人，然后他们……

<details>
<summary>Original English</summary>

**Interviewer**: Maybe in uh some other countries $10 an hour, but let's put it at 20 bucks an hour. You've got 90% compression in cost at some point when these things hit the market, which gives you plenty of room to charge an Amazon or Toyota, other partners on an hourly basis. Is that the current plan to charge per hour of utilization? You own the robot. They

</details>

**Jonathan**: 两种方式我们都做。我们为喜欢资本支出的客户提供买断方案。我们也为喜欢这种方式的客户提供“机器人即服务（Robot as a Service）”。对他们来说，这真的降低了进入门槛，也降低了风险。

<details>
<summary>Original English</summary>

**Jonathan**: We do both. We do a capex for customers that prefer that. We also do robot as a service for customers that prefer that. It's really lower barrier to entry and lower risk for them.

</details>

**Interviewer**: 机器人每小时的价格是多少？

<details>
<summary>Original English</summary>

**Interviewer**: What's the price of a robot per hour?

</details>

**Jonathan**: 我们现在还不会讨论这个问题。但我会说，显然，随着机器人在它们所做的事情上变得越来越好，它们的价值也会不断上升。同时，制造机器人的成本正在下降。这些机器人的价值实际上是由人力劳动决定的，以及支付人们从事这些工作的成本是多少。所以在很长一段时间内，这是一个非常缺乏弹性的价格。

<details>
<summary>Original English</summary>

**Jonathan**: We're not talking about that right now. But I will say like as obviously as the robots get better and better and better at what they do, their value goes up and up and up. And that's at the same time that the costs to build the robot are going down. And the value for these robots is really set by the human labor and what does it cost to pay people to do these jobs. So it's a very inelastic price for a very long time.

</details>

**Interviewer**: 所以，比较这只有数万美元的物料清单，以及目前在现代世界的西半球，工厂里的工人们每小时获得 20、30 或 40 美元的薪水……这是一个相当庞大的市场。

<details>
<summary>Original English</summary>

**Interviewer**: So between a a bill of materials, tens of thousands of dollars, currently people in factories getting paid 20, 30 or $40 per hour in the Western Hemisphere in the modern world, which is a pretty big market.

</details>

**Jonathan**: 是的，非常庞大的市场。有足够的空间让你为他们省钱，并让你获得足够的利润，

<details>
<summary>Original English</summary>

**Jonathan**: Yeah, pretty big market. Plenty of room for you to save them money and for you to make enough profit,

</details>

**Interviewer**: 去建立一个真正的企业，你知道的，

<details>
<summary>Original English</summary>

**Interviewer**: build an actual business, you know,

</details>

**Jonathan**: 建立一个真正的企业。是的。

<details>
<summary>Original English</summary>

**Jonathan**: to build an actual business. Yeah. 

</details>

### 自动化与未来劳动力的转折点

**Interviewer**: 那么让我们把话题转到你认为的时间框架上。如果我问你，在亚马逊工厂，或者如果我们要把亚马逊排除在外，因为他们是合作伙伴，不想给你惹麻烦，但在亚马逊或塔吉特（Target）这样的公司，在什么时间点工厂里的大多数工人将会是机器人？基于你所了解的情况，Jonathan，这个翻转到 51% 的临界点什么时候会发生？

<details>
<summary>Original English</summary>

**Interviewer**: So let's take the conversation to what do you think the time frame is if I were to ask you in Amazon factories or if we want to take Amazon out because they're a partner don't want to get you in trouble but an Amazon or Target like company at what point will the majority of workers in a factory be robotic when will that flip happen to 51% knowing what you know Jonathan

</details>

**Jonathan**: 我的意思是，在很多此类应用场景中，大多数工人已经是机器人了。

<details>
<summary>Original English</summary>

**Jonathan**: I mean already in a lot of these applications the majority of the workers are robots.

</details>

**Interviewer**: 确实。

<details>
<summary>Original English</summary>

**Interviewer**: Sure.

</details>

**Jonathan**: 对吧。那里有大量的 AMR（自主移动机器人），大量的传送带，大量的工业机械臂，这一点并没有改变。这种趋势还在持续增长。当然了。这只是一种新形式的自动化，就像所有其他的自动化一样，在帮助提高和建立这种生产力。

<details>
<summary>Original English</summary>

**Jonathan**: Right. There's a lot of AMRs, there's a lot of conveyor belts, there's a lot of industrial robot arms and that's not changing. That's continuing to grow. Sure. And this is just a new form of automation like all of the others that's uh helping to increase and build that productivity.

</details>

**Interviewer**: 所以，就像，你知道的，无论如何在美国我们是如何提高我们的 GDP 的？并非依靠不断增长的人口。不是的。

<details>
<summary>Original English</summary>

**Interviewer**: So like how do you know how do we in the United States anyway, how do we build our GDP? It's not a growing population. No,

</details>

**Jonathan**: 它是靠提高效率和能力。我们能够做到这一点的唯一方法就是越来越依赖它……

<details>
<summary>Original English</summary>

**Jonathan**: it's increased efficiency and capability. And the only way we could do that is more and more

</details>

**Interviewer**: 尤其是在我们国家现在，甚至在整个西半球都弥漫着反移民情绪的情况下。嗯，让我换个方式来问这个问题。在什么时间点，如果……

<details>
<summary>Original English</summary>

**Interviewer**: especially not with the anti-immigration vibes we have in the in the country right now or even in the western hemisphere. Um well let me phrase the question another way. At what point if there were

</details>

<!-- chunk 9/9 -->

### 自动化工厂的未来与人形机器人的定位

**Host**: ……有数以百万计的人在工厂里从事着分拣包裹的工作，这个数字未来会下降到五十万吗？这会是一个需要三年、四年还是五年的时间跨度呢？

<details>
<summary>Original English</summary>

**Host**: ... million people working in factories sorting packages does it go down to 500,000? Is that a three, four, five year?

</details>

**Jonathan**: 我认为我们其实已经做到这一点了，对吧？但是随着这些新技术的不断涌现，这种自动化的趋势将会一直持续下去。你要知道，总有一天，我们会看到一辆自动驾驶的卡车缓缓驶来，然后面对的是一个完全“熄灯”的、纯自动化的包裹分拣工厂，在完成任务之后，接着你又会看到这辆自动驾驶卡车再次驶离。到了那个发展阶段，很可能就是各种专用的自动化设备在负责做这些事情，因为它们能够全天候24/7不间断地执行任务。在那种场景下，投入一个人形机器人去工作反而没有意义。对于那种极其特定的单一任务来说，人形机器人并不是最高效的解决方案。人形机器人的真正用途在于走进属于人类的复杂环境，去执行适应人类的工作流程。因此，当这个包裹分拣工厂完全实现自动化的时候，世界上也还有一大批其他的工厂依然是传统的模式，它们依然需要在人类曾经工作过的地方逐步引入自动化。但与此同时，我们现在的研发工作也正在向零售店、杂货店、医院和建筑工地等领域拓展，以及将包裹直接送到你家门前的台阶上，而这些地方永远都会是属于人类的生活环境，对吧？还包括印刷厂的堆场，呃，以及诸如此类的各种应用场景。

<details>
<summary>Original English</summary>

**Jonathan**: I think we've already done that, right? But looking for and but with these new it's going to just continue. You know, someday there's going to be an autonomous truck that drives up and have a completely lights out autonomous package sortation factory and then you know an autonomous truck leaving again. And at that point, it's probably specialty automation doing those things because it's just 24/7 doing it. And a humanoid doesn't make sense. It's not the most efficient thing for that specific task. A humanoid is useful for walking into human environments doing human workflows. So by the time this one factory is entirely automated, there's also a whole bunch of other factories that still are, you know, legacy and still, you know, need automation where humans were. But then we're also working now in retail and grocery stores and hospitals and construction sites and delivering packages to your front door, which is a forever human environment, right? Print yards, uh, and that kind of thing.

</details>

**Host**: 那确实将会成为一个非常有趣的场景。

<details>
<summary>Original English</summary>

**Host**: That's going to be an interesting one.

</details>

**Jonathan**: 是的，没错。

<details>
<summary>Original English</summary>

**Jonathan**: Yeah.

</details>

**Host**: 因为现在任何只要稍微关注过最新一代人形机器人发展的人，都能很明显地看出，传统工厂正在不可逆转地走向无人化的“熄灯”时代。但在目前这个阶段，绝大多数人大概还无法在脑海中想象出这样一幅画面：一辆Waymo的无人驾驶出租车，或者一辆Uber的自动驾驶汽车缓缓停下来，然后从车里面竟然走出来一个机器人。

<details>
<summary>Original English</summary>

**Host**: Because it's fairly obvious to anybody who has even looked at the latest generation of humanoid robots that the factories are going lights out. Most people are incapable at this point of imagining a Waymo robo taxi, an Uber self-driving car, and a robot getting out.

</details>

**Jonathan**: 是的。

<details>
<summary>Original English</summary>

**Jonathan**: Yeah.

</details>

**Host**: 并且这个机器人还要把包裹一直送到你的家门口。

<details>
<summary>Original English</summary>

**Host**: And bringing the packages to your doorstep.

</details>

**Jonathan**: 这件事情在未来绝对会发生。

<details>
<summary>Original English</summary>

**Jonathan**: That's going to happen.

</details>

**Host**: 绝对会的。说回正题。你们现在正在和合作伙伴一起开发这个功能吗？你不用透露具体是谁，但是……

<details>
<summary>Original English</summary>

**Host**: Absolutely. Going back. Are you working with folks on that? You don't have to say who, but

</details>

**Jonathan**: 你知道吗？那其实是我们最早和福特汽车（Ford）一起探索的应用场景之一。在网上还有一段非常棒的视频，展示了我们第一代Digit机器人从一辆汽车里走出来，走到某个人家的前廊，然后把包裹稳稳地放在那里，它甚至能自如地上下楼梯以及完成所有的相关动作。所以，我们在大约七年前就已经能做到那样的事情了，大概就是那个时候。呃，但我个人并不认为它是最佳的首发应用场景，也不是最佳的初始切入市场。因此，这个项目肯定还在我们的长期路线图上。

<details>
<summary>Original English</summary>

**Jonathan**: you know what? That was one of our very first use cases that we explored with Ford. And there's a nice video online of our very first digit robot getting out of a vehicle, walking up to someone's front porch and dropping a package there, stairs and everything. So, we could do that like this was seven years ago, something like that. Uh, but I don't think it's the best first use case or the best first market. So, it's on our road map for sure.

</details>

### 机器人的非显性应用与积极社会影响

**Host**: 但对于我们目前正在做的事情来说，这已经是一个部署产品的庞大市场了。我们要从那里起步。当你考察各种不同的应用时，我们这些非业内人士认为有些应用是显而易见的；但是基于你过去二三十年在这个行业里积累的渊博知识和经验，你认为有哪些是一两个对大众来说并非显而易见、但却对世界有极其深远且积极影响的应用场景呢？

<details>
<summary>Original English</summary>

**Host**: But such a big market for deploying with what we're doing right now. We're going to start there. How do you when when you look at applications, we know applications that seem obvious to us not being in the industry, but knowing what you know over two or three decades, what do you think is a a use case or two that are nonobvious, but that would be incredibly world positive?

</details>

**Jonathan**: 我一时间不知道该怎么界定什么才算是“不明显”的。我的意思是，仅仅是去拿起东西，然后把它们放到另一个地方去，这就已经是一个非常巨大的应用场景了，它能够把人们从机器人学中经典的“3D”工作中彻底解放出来，也就是那些枯燥（dull）、肮脏（dirty）和危险（dangerous）的苦差事。

<details>
<summary>Original English</summary>

**Jonathan**: I don't know what to say what's not obvious. I mean, just picking up stuff and putting them somewhere else is such a huge use case that frees people from the classic 3Ds of robotics, the dull, dirty, dangerous kind of stuff.

</details>

**Host**: 枯燥、肮脏、还有危险。

<details>
<summary>Original English</summary>

**Host**: Dull, dirty, and dangerous.

</details>

**Jonathan**: 没错，机器人学的“3D”。

<details>
<summary>Original English</summary>

**Jonathan**: The 3Ds of robotics.

</details>

**Jonathan**: 我真的非常希望有一天，你知道，就像我们的孩子在未来回顾现在，看着人们今天正在做的一些工作，能产生像我们回顾 20 世纪初（1900年代）的煤矿工人时一模一样的感受，我们会感慨地说，“我真不敢相信以前人们竟然还要做那种恶劣的工作。”你也知道，今天人们所拥有的很多角色和工作已经比过去好太多了。大家的生活质量已经好太多了。今天人们拥有的很多工作，在 1900 年是绝对无法想象的，而且它们往往要优越得多。我深信，那也正是未来将要呈现在我们面前的美好景象。

<details>
<summary>Original English</summary>

**Jonathan**: And I really hope that we look, you know, like our children look back on now and look at some of the jobs that people are doing today that I really think of as robot jobs the same way we look back on like coal miners in the 1900s and say, "I can't believe people did that work." And you know the number of roles and things that people do today are so much better. The quality of life is so much better. The jobs that people have today that you couldn't have imagined in 1900 often are just so much better. I think that that's how the future is going to look for us.

</details>

### 新时代的职业机遇与蓝领路线

**Host**: 你现在依然还是一名机器人学教授。

<details>
<summary>Original English</summary>

**Host**: You're still a professor of robotics.

</details>

**Jonathan**: 是的。

<details>
<summary>Original English</summary>

**Jonathan**: Yes.

</details>

**Host**: 你的研究生项目里汇聚了数百名，或者说一百多名优秀的学生。

<details>
<summary>Original English</summary>

**Host**: You have hundreds of people in this graduate program or over 100.

</details>

**Jonathan**: 是的，我们确实有。

<details>
<summary>Original English</summary>

**Jonathan**: Yes, we do.

</details>

**Host**: 嗯哼。对于那些正在收听本期节目的年轻人来说，尤其是那些对自己的未来发展和职业选择感到担忧的人，这似乎是一条极具潜力和不可思议的职业道路。

<details>
<summary>Original English</summary>

**Host**: Mhm. For young people who are listening to this, who are worried about their future and careers, this seems like an incredible career path.

</details>

**Jonathan**: 这是一个非常庞大的历史机遇。我们目前正生活在一个充满变革的时代。每当出现像这样深刻的变革时期时，刚刚走出校园的年轻学生就会天然具备一种优势。因为所有那些已经拥有二三十年职业生涯、并且深谙过去传统做事方式的资深人士，他们也不得不重新回炉，去学习现在事物发展的新方式。是的。因此，学生们是拥有独特优势的，要准确预测10年后人们的职业到底会变成什么样是很困难的，但是，只要学生们能够围绕工程学建立起一些核心的技能组合，这些技能就一定能找到适用的场景，并拥有广阔的用武之地。

<details>
<summary>Original English</summary>

**Jonathan**: It's a massive opportunity. We live in a time of change. Anytime there's a time of change like this, students coming out have an advantage because all the people who have this 20, 30 year career and how know how the way things were done, they have to learn how the way, you know, the way things are coming up now, too. Yeah. So students have an advantage and it's hard to predict exactly all the things that people you know the way the careers are going to look in 10 years but if students just build some of the core skill sets around engineering it's going to be applicable and use form.

</details>

**Host**: 所以刚才提到的是机器人领域的博士或硕士等高等教育路线。那么，在这个领域中是否还存在着另一种版本的职业道路，比方说，更偏向于下一代的工具带和蓝领路线，这就等同于现在的电工、暖通空调（HVAC）技术工人、木匠或者是一线的承包商？

<details>
<summary>Original English</summary>

**Host**: So there's the PhD mast's version of robotics. Is there another version that is let's say a little more generation tool belt bluecollar the equivalent of being an electrician or working on HVAC or a carpenter or a contractor?

</details>

**Jonathan**: 是的，绝对存在这样的路线。

<details>
<summary>Original English</summary>

**Jonathan**: Yes, absolutely.

</details>

**Host**: 那具体是一种什么样的职业，它未来会发展成什么样子？

<details>
<summary>Original English</summary>

**Host**: What is that and what will that be?

</details>

**Jonathan**: 比如负责组装和制造机器人的机器人操作员。因为机器人目前显然还不能完全自行组装自己，你知道的。所以，未来会有大量的机器人制造岗位，而且正如刚才所说，在日常的机器人操作和大规模部署环节，也存在着海量的工作机会……

<details>
<summary>Original English</summary>

**Jonathan**: Robot operators assembling and building robots. The robots can't assemble all themselves yet, you know. So, there's a lot of manufacturing and and again, you know, robot operations and deployments. There's a lot

</details>

**Host**: ……机器维护，“铁疙瘩”（clanker）维护员。

<details>
<summary>Original English</summary>

**Host**: maintenance clanker clanker maintenance.

</details>

**Jonathan**: 绝对是的。话说回来，Clanker（铁疙瘩）是个带有贬义色彩的词吗？

<details>
<summary>Original English</summary>

**Jonathan**: Absolutely. Is clanker a derogatory term?

</details>

**Host**: 我也不清楚。这应该是一个迪士尼的，你知道，注册商标词。所以，

<details>
<summary>Original English</summary>

**Host**: I don't know. It's a Disney, you know, trademark term. So,

</details>

**Jonathan**: 哦，真的是这样吗？

<details>
<summary>Original English</summary>

**Jonathan**: Oh, is it really?

</details>

**Host**: 可能是吧。

<details>
<summary>Original English</summary>

**Host**: Probably.

</details>

### 产品形态与科幻文化

**Host**: 可能是。来到最后一个问题。我觉得我们都是同一批出生于 X 世代的人。你，你知道的，《星球大战》里的那个格里弗斯将军（General Grievous）。

<details>
<summary>Original English</summary>

**Host**: Probably. Final question. I think we're of the same Gen X. You, you know, General Grievous from the Star Wars characters.

</details>

**Jonathan**: 就是那个由杜库伯爵（Count Dooku）亲自训练，掌握了绝地武士黑魔法的那位，对吧？

<details>
<summary>Original English</summary>

**Jonathan**: You trained in the Jedi dark arts by Count Dooku, right?

</details>

**Host**: 就是那个能够同时挥舞三把、四把甚至六把光剑的角色。那么这是一个半开玩笑的问题：为什么不设计出拥有四条或六条手臂，并且能同时面向所有方向的机器人呢？

<details>
<summary>Original English</summary>

**Host**: Able to yield three or four six lightsabers at a time. Is the half serious question. Why not have four or six arms facing all directions?

</details>

**Jonathan**: 这是一个非常好的问题。所以，我会说，你知道，当我们从第一性原理出发，去思考如何制造出最简单的机器人来完成指定任务时，对吧？只有一条手臂是不太够用来拿起大件物品的。你只能用它抓起一些小东西。而有了两条手臂，你现在就可以稳稳地拿起大件物品了。如果在这个基础上再强行加上第三条手臂，其实很难看出它能提供足够的效用，来证明把它整合进去是物有所值的。至于说，你知道的，进一步增加到四条甚至五条手臂。那将会带来大量极其复杂的协调工作和许多额外的系统复杂性。但这又能让你额外多做些什么有价值的事情呢？我不知道。也许未来我们确实会看到那种复杂的设计，但它的出现必须是由某种真实且迫切的需求来驱动的。

<details>
<summary>Original English</summary>

**Jonathan**: It's a good question. So, I would say that, you know, as we think about the first principles of what how to make the simplest possible robot to do the task, right? One arm is not quite enough to pick up big things. You can only pick up small things. Two arms now you can pick up big things. Adding a third arm, it's hard to see the enough utility to make it worth fitting it in. And then, you know, go to four to five. There's a lot to coordinate and a lot of extra complexity. But what else does it make you do? I don't know. Maybe we'll see that, but it's going to have to be driven by a real need.

</details>

**Host**: 好的。在整个科幻历史上，你最喜欢的机器人角色是谁？

<details>
<summary>Original English</summary>

**Host**: All right. Favorite robot in science fiction history.

</details>

**Jonathan**: 可能是《机器人总动员》里的瓦力（Wall-E）和伊娃（Eve）。我个人非常喜欢那种带有使命感愿景的设定，这些机器人就是执着地、不断地尝试去构建、创造，并完成它们最初被设计出来的使命和工作。

<details>
<summary>Original English</summary>

**Jonathan**: Probably Wall-E and Eve. I love kind of that vision of these robots just continuing to try and build and create and do what they were designed to do.

</details>

**Host**: 我也很喜欢大白（Baymax）。大白是个相当了不起的角色。

<details>
<summary>Original English</summary>

**Host**: I love Baymax, too. Baymax is pretty fantastic.

</details>

**Jonathan**: 等等，等等。谁是……谁是大白？

<details>
<summary>Original English</summary>

**Jonathan**: Wait, wait. Who's Who's Baymax?

</details>

**Host**: 大白，出自，呃，那部电影叫什么来着？旧金山（San Fransokyo）里的，出自，呃……

<details>
<summary>Original English</summary>

**Host**: Baymax from uh what is it? San Francio from uh

</details>

**Jonathan**: 哦，对的，当然想起来了。嗯，我确实知道这个显然是被创造出来帮助别人的医疗机器人。而且我，我很喜欢电影里他们表现出它只会严格去做它被编程去执行的事情的那种方式。我是说，在电影的某个情节里，他们删除了它所有的记忆卡，它的眼睛瞬间变成了红色，然后就变成了一个极其危险的战斗机器。其实，这在现实中是非常真实的一面。你知道，对于你的软件系统，你必须要有非常到位的安全防护措施。你必须在这些复杂的机器上设置强制急停（estop）功能。

<details>
<summary>Original English</summary>

**Jonathan**: Oh, yes, of course. Um I do know who this robot that's very clearly there to help. And I I love how they kind of show that it it does what it's programmed to do. I mean, at one point they remove all its memory and it turns red and now it's dangerous. Well, that's very real. You know, your software, you have to have the safeguards in place. You got to have the estop on these things.

</details>

**Host**: 所以，你会自然而然地去思考它的“机器人第一法则”和最高指令。

<details>
<summary>Original English</summary>

**Host**: So, you think about the prime directives.

</details>

**Jonathan**: 是的。基本上就是这样考虑的。

<details>
<summary>Original English</summary>

**Jonathan**: Yeah. Basically, yeah.

</details>

### 安全保障与行业号召

**Host**: 那么你如何确保这些正在经历类似工业安全流程的机器产品绝对安全呢？就是为了确保，哇，里面必须要有一个监控电路，每个机器人上都必须要有一个物理急停开关，所有这些东西的存在，能够百分之百确保这些机器人绝不会伤害人类。Jonathan，我知道你们公司目前正在招聘。这家公司的名字叫 Agility Robotics。呃，如果有人正在寻找一份工作，那是一个非常有趣的工作场所。

<details>
<summary>Original English</summary>

**Host**: How do you make sure that these things going through kind of the industrial safety process to make sure that boy there's a supervisory circuit, there's a a estop on every robot, all of these things that make make the robots, they could just really never harm a human. Jonathan, I know you're hiring. Agility Robotics is the company. Uh, and if people are looking for a gig, fun place to work.

</details>

**Jonathan**: Agility 是一家非常棒的公司。我们在俄勒冈州的塞勒姆（Salem）设有一个办公地点，那是我们最初创办这家公司的地方，也是我现在所在的地方。呃，我们即将在加州弗里蒙特（Fremont）开放一个全新的设施，那是一个风景极其优美的绝佳地点。我们在那里正在紧锣密鼓地进行大量的机器人行为开发和测试工作。所以，那里会有成群的机器人在一整天不停歇地工作，你也可以随时进来亲手参与到上面的研发工作。此外，我们在匹兹堡（Pittsburgh）也有一个重要的办公地点。

<details>
<summary>Original English</summary>

**Jonathan**: Agility is great. And we have location in Salem, Oregon, where where the we started, where I am. Uh, we have a uh new facility we're opening in Fremont, California, which is just a beautiful place. And that's where we're doing a lot of robot behavior development. So, there will be robots working all day long, and you can come in and be working on. And we have a Pittsburgh location as well.

</details>

**Host**: 哦，对了。就在卡内基梅隆大学旁边。太赞了。是的。三个非常棒的研发中心。呃，所以如果你是一个对未来充满憧憬的年轻人，或者你正身处机器人领域，那里是非常适合施展才华的地方。而且，呃，如果你对自己的未来还有些担忧的话，那就去读一个机器人学相关的博士或硕士学位吧。各位听众，要提前滑向冰球将要到达的那个地方，而不是它现在所在的位置。

<details>
<summary>Original English</summary>

**Host**: Oh, right. Right by Carnegie Melon. Amazing. Yeah. three great centers. Uh so if you're a young person or you're in the robotics field, pretty great place to work. And uh if you're worried a little bit about your future, go get a PhD or a masters in robotics. Skate to where the puck is going, folks.

</details>

**Jonathan**: 完全正确。

<details>
<summary>Original English</summary>

**Jonathan**: Right.

</details>

**Host**: 很高兴能认识你，也非常感谢你今天与我们分享了这么多的专业知识。

<details>
<summary>Original English</summary>

**Host**: Great to have met you and thank you for sharing all your knowledge.

</details>

**Jonathan**: 谢谢你。

<details>
<summary>Original English</summary>

**Jonathan**: Thank you.

</details>

**Host**: [音乐声响起] 我要全押了（I'm going all in）。

<details>
<summary>Original English</summary>

**Host**: [music] I'm going all in.

</details>