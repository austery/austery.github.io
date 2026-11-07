---
author: TED
date: '2026-07-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=v0BiDmPloBs
speaker: TED
tags:
  - public-safety
  - surveillance-technology
  - privacy-rights
  - data-governance
title: 每个街角都有摄像头，真的能让我们更安全吗？
summary: Flock Safety 创始人 Garrett Langley 在 TED 演讲中探讨了通过人工智能摄像头、无人机和车牌识别技术重构公共安全系统的可能性，分析了从传统“主观警务”向数据驱动的“客观警务”的转型，并深度剖析了该技术在提升破案效率、减少犯罪与保障隐私边界、防范大规模监视之间的权衡博弈。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Flock Safety
  - TED
products_models: []
media_books: []
status: evergreen
---
### 每个街角都有摄像头，真的能让我们更安全吗？

### 黄金生还窗口：数据驱动的精准搜救
首先，演讲者讲述了一个发生在田纳西州农村的真实故事。一位祖母在清晨醒来，走进她11岁孙女的房间，却发现床空无一人。现场没有留下任何字条或线索，这让她的心跳瞬间加速。祖母立刻拨打了911报警电话。随后赶到的侦探发现现场没有任何暴力入侵的迹象，唯一的线索只剩下街区尽头安装的一台 **车牌识别相机**（License Plate Reading Camera: 用于自动捕获并识别车辆牌照字符的智能影像采集设备）。侦探在手机上检索了事发当晚的数据，锁定了一辆唯一的嫌疑车辆。在对车牌进行查询后，发现该车主是一名登记在案的性侵犯。侦探立即登录系统追踪这辆车，发现它正在75号州际公路上向佐治亚州方向行驶。由于情况紧急，侦探驾车狂奔，在跨越州界线时成功拦截了该车辆。经过激烈的搏斗，侦探在嫌疑车后座发现了被捆绑但依然生还的女孩。随后的搜查发现，嫌疑人住宅中准备了所有用于伤害并处置尸体的工具。女孩政策能在今天活下来，完全是因为侦探掌握了车牌号码和行驶方向这两个关键线索。

<details>
<summary>Original English Source</summary>

I'm going to start with a story um speaking to a grandmother in rural Tennessee and she was taking care of her 11-year-old granddaughter. So, she wakes up, she walks into her room. The bed's empty. She looks around. There's no note. There's nothing. If your heart's not racing right now, should be. She calls 911. detective arrives. [snorts] No sign of force. There's nothing except one thing that he remembered. There's a flock camera just down the street. So, he pulls out his phone and runs a search for the night and finds one car. He runs that tag and it's his worst nightmare. It's a registered sex offender. So, he logs into Flock and he's looking for this car and he sees the car is traveling down I75. If you're not familiar with Tennessee and Georgia, that's the connecting state. It's the highway. The person's on the highway. The detective doesn't know what to do, so he does whatever hero does is he moves into action. He jumps in his car and races down I75. As he approaches the interstate line, he sees the vehicle. Violent struggles pursues and at the end, he hears crying. And the girl's in the back. She's bound, but she's alive. They went on to go search the suspect's house, and the nightmare got scarier. Everything one would need to not only assault, but dispose of the body was there. Now, that girl's alive today because a detective had two things. He had a license plate and he had direction to travel.

</details>

在建立这种通过技术快速锁定嫌疑目标的思维后，具体的系统设计起源于演讲者自身的经历。

### 破案的关键：以技术沉淀客观证据
这个令人心惊的案例只是全美每天发生的成千上万起案件中的一个缩影。演讲者 Garrett Langley 九年前在亚特兰大创立了 Flock Safety，起因正是因为这种犯罪分子极易脱罪的普遍社会现象。当时在亚特兰大，盗窃车辆有高达80%的概率逃脱惩罚，而谋杀案也有50%的脱罪率。在向亚特兰大警察局深入调研后，警长告诉他：“问题不在于冷漠或不够努力，而在于证据。如果我们能拿到车牌，就能抓住这些人。”于是，演讲者与来自佐治亚理工学院的两位好友合作开发并部署了第一台车牌识别相机。仅仅两个月后，他们就成功破获了第一起案件，这便是 Flock 公司的起点。如今，该公司已不仅局限于相机，而是扩展到了无人机、音频检测设备以及将这一切连接在一起的软件系统。其核心逻辑在于，当车辆驶过时，系统会生成一个**车辆特征识别**（Vehicle Signature: 包含车辆品牌、型号、颜色等可识别特征的数字化标识），记录品牌、型号、颜色等一切侦探会注意到的特征，从而协助捕获犯罪嫌疑人。

<details>
<summary>Original English Source</summary>

This, for me, is one of thousands of stories I sadly hear about every day in America. I started Flock 9 years ago because of this exact type of problem. See, I live in a city called Atlanta, and I was frustrated. Crime felt too easy to get away with. It didn't make sense to me that you could steal someone's car and have an 80% chance of getting away with it. Or you could kill someone and have a 50% chance of getting away with it. So, I kept pushing. I kept pushing and eventually I found a major Atlanta Police Department who told me, \"Mr. Langley, it's not apathy. It's not effort, it's evidence. If all we had was a license plate, we could catch these people.\" So, I did what engineers did. I built a license plate reading camera. It sounds simple. Um, but I called two of my best friends from Georgia Tech and we built this camera. He said, \"You have to have a license plate.\" So, we did that, put it up in my neighborhood, and about two months later, we solved our first crime. And that was the beginning of Flock. And now, as you've heard, the company has grown quite a bit since then. We do more than cameras. We build cameras now. We build drones. We build audio detection devices. We build software that connects it all together. And the concept is actually still this simple 9 years later. Car drives by. We do what we call a vehicle signature. We look for the make, the model, the color, anything a detective would notice. And then you catch the bad guy.

</details>

随着技术的普及与多传感器融合的发展，警务模式迎来了颠覆性的变革。

### 警务范式转型：从主观经验到客观警务
一位华盛顿的警察局长曾向演讲者表示，这种多传感器融合的技术对公共安全的颠覆性“堪比DNA技术”。在传统模式下，**主观警务**（Subjective Policing: 依赖执法人员主观直觉在特定街区巡逻的偏好性执法）是一种高度主观的活动，警察在他们认为“可疑”的社区巡逻，寻找他们认为“可疑”的行为，这便是偏见的根源。而引入 Flock 系统后，执法转变为**客观警务**（Objective Policing: 基于客观数据和确凿证据而非主观判断进行的执法活动），警报只针对被盗车辆、涉拐的安珀警报（Amber Alert）或针对失踪老人的银色警报（Silver Alert）等客观事实触发。
以科罗拉多州的一起真实案件为例：一家李维斯（Levi's）奥特莱斯店发生劫案，911接警员描述嫌疑人驾驶一辆“喷涂成黑蓝相间的白色货车”。警方将这一特征输入系统，全城的摄像头立即变身“侦探”协同搜索，同时派遣了一架时速65英里、在400英尺高空飞行的无人机进行空域排查。在摄像头锁定车辆后，无人机进行空中尾随，而嫌疑人对此毫不知情。这使得执法人员能够从容、精准地包抄，避免了因“假定最坏情况”而强行突扑导致的公共风险。最终，从接警到在第二家奥特莱斯将嫌疑人逮捕，整个过程仅耗时21分钟。

<details>
<summary>Original English Source</summary>

And that's what I thought we were doing, right? And then I was speaking to a police chief not too far from here in Washington. And he said, \"No, no, Mr. Langley, this is more than about fighting crime. This is as transformational as DNA.\" And candidly, I was confused. It's a camera. What's the rub? And he said, \"Well, look, let me explain to you how poling used to work.\" Historically, poling is a subjective exercise. You drive around suspicious neighborhoods looking for suspicious activity, and ah, there is the root of the bias. what's suspicious to me is different than her and different than him. That doesn't seem very good. And so the chief was explaining to me that now with Flock, it's objective. That is a stolen car. That is a car that has a child in the back of it. That is the car that has an Amber Alert or a silver alert. So we've moved the way policing works. It's pretty incredible. But let me give you a real life example. So now we're going to go all the way to Colorado. So, it's a 911 call. It's a Levis outlet. And this might be the most important thing I say all day. The 911 is describing the getaway car as a white van spray painted black and blue. Here's a pro tip. If you're going to commit a crime, do not spray paint your vehicle. Do it in a Camry or Corolla. Something simple, right? So, the 911 call comes in. They have this van. So, they go into this our product and search for a vehicle. They can type in anything they want. White van, spray paint, anything that makes sense. Now, what's cool is it turns every single camera into a detective. Now, every camera in the city is looking for this white van. The second thing they do is they launch a drone. So, just like Adam, launch the drone up in the air. The drone's flying at 400 ft, 65 mph trying to find this white van. Now, a camera eventually finds them. Drone over. Now, in a normal reaction, as a law enforcement officer, you have to assume the worst case scenario. Is this person armed? Probably. Is the public at risk? Probably. So, you come in hot. But with a drone overhead flying at 400 feet, the suspect has no idea. Officers can respond with precision and with calmness. So, from start to finish in 21 minutes, from a 911 call to Levis's outlet, tracking the car all the way to a second outlet, there was an arrest.

</details>

这种快速响应和数据连接的能力，吸引了美国许多大城市和顶尖企业对其进行大规模部署。

### 效率与边界：大规模部署下的社会信任
以旧金山为例，两年前该市陷入公共安全危机，随后全面部署了 Flock 的车牌相机、无人机、视频监控及整合软件。旧金山市长将这种多传感器融合描述为公共安全的革命性转型，如今旧金山的犯罪率下降了25%，凶杀率达到了70年来的最低水平。
然而，在技术规模不断扩张的同时，争议也随之而来。公众普遍担忧其是否侵犯隐私、构成违宪，甚至助长**监控国家**（Surveillance State: 政府利用高科技手段对全体公民进行全方位、系统性监控的国家形态）的形成。针对违宪质疑，过去两年中共有30起相关法庭诉讼，法院最终一致裁定该技术并未违宪。其法理依据在于，该系统并非实时追踪特定“个人”，而是记录公共道路上固定位置的“车辆”，这在法律框架内属于合法公共场所摄像。

<details>
<summary>Original English Source</summary>

Now, if you zoom this all the way out, some of the biggest cities in America, some of the biggest companies in America rely on flock to keep them and their employees and their citizens safe. Two years ago, San Francisco was in a crisis, as many of you probably know. They deployed everything Flock has. License reading cameras, drones, video cameras, our software that ties it all together. And Mayor Lur described this fusion of sensors as a transformation in public safety. And if any of you live in the city, you know that it feels safe. All of a sudden, crime is down 25%. Homicide is the lowest rate it's been in 70 years. So, this all seems really good, right? Well, while the company's scale has grown and a lot of things have changed for me, one thing's been very consistent. There is inevitably some part of this audience today who's saying, \"I don't know. This snitching ass startup kind of doesn't make sense to me.\" And this was our first ever press coverage. And I was so proud. I framed this and my poor mother was like, \"Why are you framing this?\" And I'm like, \"Because it's a reminder that when you work on important things, some people will disagree and that's okay. It means you should work harder.\" And so when I talk to these opponents, and I've got to know them many of them over the years now, they tend to have three big issues with flock. Whether this is constitutional violation, what does this mean to my privacy? And are you building mass surveillance? These are pretty good questions. Let's hit the easy one. Constitutional. 30 court cases over the last two years. Every single one of them has unanimously said this does not violate the constitution. Why? We're not tracking a person's in real time. We are tracking a fixed location. Not a lawyer, but I'm going to go with the courts. So, I'm going to check the box on.

</details>

在应对宪法合规的同时，如何构建防范技术滥用的安全阀成为设计核心。

### 数据治理机制：所有权、保留期与双向审计
为了防止技术滑向无节制的监控，Flock 在产品架构上引入了严格的**数据治理**（Data Governance: 针对数据资产的获取、使用、保护和删除所制定的系统性管理规范）机制。首先，确立了“客户所有制”，数据完全归部署城市的政府所有（如旧金山的数据归旧金山市政府，而非 Flock），严禁商业化转售。其次，实施了“30天强制过期删除”的极短数据保留期，将数据从资产转化为需要按期销毁的负债。最关键的是“双向审计机制”：系统内所有操作均会生成永久不可篡改的**审计日志**（Audit Log: 记录系统中所有用户操作和事件以供安全审查和追责的不可篡改日志记录）。
这种机制的威力在具体案例中得到了体现。去年，北佐治亚州的一位警察局长试图利用 Flock 系统追踪其前伴侣，这属于严重滥用。但正是由于 Flock 审计日志的存在，佐治亚州调查局（GBI）获取了确凿证据，该局长随后被起诉并判刑入狱。这一案例表明，当技术被赋予高度的责任与可追溯性时，滥用行为将无处遁形。此外，由于美国拥有多达18,000个独立的警察部门，各辖区长期存在“数据孤岛”，Flock 建立的全国性协作网络不仅提高了跨区办案效率，也让跨辖区的监督审计成为可能。

<details>
<summary>Original English Source</summary>

Second one's privacy. This is actually a really good question because nine years ago, I did not have a degree in criminal justice. I had no experience. I was an engineer that just wanted to build a product to help fight crime. But when we sat there and said what if we are really successful what could go wrong. So we started looking what the industry did. So the first thing we asked was what about data ownership? Who should own this data? This is a lot of data. Historically companies my competitors own the data and then they resell that data for other use cases. In flock model the customer always own the data. So if you live in San Francisco it's San Francisco's data not flocks. The second was retention. Well how long should this data exist? Historically, companies in this industry stored the data in perpetuity. That seems to me more like a liability than an asset. So, we delete the data at 30 days. If cities and states have laws that say it should store longer, we do that. Shorter, we do that. The third is around accountability. With everything that's powerful should come heightened responsibility. Every action inside a flock is audited and stored in perpetuity. to every action an officer takes. And sadly, three officers were arrested last year for abusing this system. Now, I think if anything that speaks very poorly on the law enforcement industry, but it is a reminder that when you build tools to hold people accountable, it starts to work. And then the last one, and this is the most interesting to me, if you go to a place like the UK, there's 45 police departments. You go to Australia, there's eight. France, there's two. And does anyone want to guess how many police departments are in America? You're way off. 18,000. Duh. Okay, this is the problem. You literally can commit a crime in city A and drive to city B and they're like, \"Oh, who are you?\" You leave state A to state B, and they're like, \"We have no record of you.\" This entire problem is a data problem. These cities have not historically worked together. They moved to the cloud less than 10 years ago, 5 years ago. And so one of the biggest criticisms of Flock is that we create this national network of data that allows local law enforcement to work together. It's a uniquely American problem.

</details>

在构建了严密的数据治理边界后，关于技术普及与社会权利的讨论走向了更深层次的博弈。

### 安全非特权：大众监视与社会权利的终极博弈
面对更广泛的**全景式监控**（Panopticon: 一种使监视者能够随时观察所有被监视者而自身不被察觉的监控体系）之问，演讲者指出，社会大众对手机定位追踪（如 Google Maps、Uber 收集的实时精确位置）习以为常，却对公共道路上的车牌相机充满警惕，这部分源于物理相机的可视性。在公共安全的抉择中，不同社会给出了不同的答案：在富人区筑起9英尺高墙、雇佣60万私人保安的南非，安全成为了有钱人的特权，而穷人只能默默承受犯罪代价；而在每年仅有数十起凶杀案的日本东京，安全是一项人人都享有的基本社会权利。
演讲者强调，安全不应受到肤色、政治立场或收入水平的影响，而应成为一项普惠的社会基本权利。然而，正如 TED 主持人随后在对话中总结的，这种强大的 AI 赋能监控技术如同一把双刃剑，技术本身的演进是客观的，但如何在使用它的过程中保持透明度、防止追踪合法抗议以及界定公权力边界，需要全社会进行持续的集体对话，在保障生命安全与维护公民自由之间寻找微妙的动态平衡。

<details>
<summary>Original English Source</summary>

Third question that I get, right? So we covered the Constitution, we covered privacy. Now the big one, surveillance state. Is this a creation of a new surveillance state? You know, look, I think everyone in this room probably has a cell phone. And what if I told you that someone with mediocre computer software skills could build a product that tracks your exact location in real time down to a few feet because all of you use Google Maps and Uber and any device that has access to location. And so I think about the tooling that we ask our local law enforcement to use and we give them a weapon, a gun, a taser, yet we're afraid to give them a camera that reads a license plate on a public road. I'm not saying that it's not a choice. I'm just saying that for me, the trade-off is I don't know how many more 11-year-old girls need to be kidnapped or human trafficking rings or silver alerts or Amber Alerts we have to go through before we say enough is enough. Now the now the beauty of America though is that every city, state, county gets to pick. It's not my choice. I live in Atlanta. I vote. You should vote. The challenge is that when you decrease surveillance and in effect decrease safety, it impacts certain parts of the community more than others. If you are affluent in South Africa, you have 9 foot walls. You have private security guards. are 600,000 private security guards in South Africa, more than the military and police combined. So if you are affluent in South Africa, it is a beautiful place to live. You are crime free. And if you are not affluent, crime is simply the cost of being alive. Now if you transpose that to a place like Tokyo, beautiful city, there's a few dozen homicides a year. Whether you go to work at 2 a.m. or 8 a.m., you feel safe. It just doesn't matter. And so America is this like very interesting conundrum in the middle. We have the law enforcement infrastructure we need to be safe. Yet we haven't made to me the most important decision as a society which is that safety should not be a privilege. Safety should just be a right. It should not matter the color of your skin, your political affiliation, or your income level. Everyone, in my opinion, deserves the right to be safe. Thank you very much.

[applause]

>> It's so interesting persuasively argued. But when you sell these systems to law enforcement, how strongly do you feel you have the right to limit what they can do? Because you you've made a powerful case for these things used the right way, but everyone here can also imagine them used the wrong way. Here's a protest. you know that cameras do do things that someone's cell phone doesn't do. You can detect individuals etc. Are you able to restrict what they do or is it just you sell the system and then it's over to you act within the law my friends.

>> Yeah. So I actually want to answer your question in two parts. The first is when I I was having this debate with our team because people were asking why do some people dislike flock but not these other things. I said you can see flock. I guarantee you if you go to our website and look at what our camera looks like and you go back home if you live in America, you will see our cameras everywhere. They're easy to spot, but your cell phone you just you're oblivious to all the tracking that exists online. So, you forget about it. But to answer your question, um we do have restrictions. Now, obviously there's this thing called the constitution which we care a lot about. There's state law, there's local law, but then there's things that we just don't feel comfortable with. And so we do set in kind of our own policy framework and then just like most technology companies, we have a full team of attorneys who actually think about this stuff full-time because our customers are just not that far the adoption curve.

>> I mean, how often do do you or someone on your team hear of something that is being done with your technology that makes you uncomfortable?

>> Three times last year.

>> Like to me it it is horrible that in the case was I'll pick on my own home state because I live in Georgia. Uh, there was a police chief in Northern Georgia that used Flock to track an ex partner. It's It's horrible. But then I'm reminded that the GBI used Flock's audit log to investigate that chief and he's now in jail. And and so I think the thing I think about to your question is like if Flock did not exist, he was probably a bad person. He was going to do this one way or another. And so I look at the 1 million plus cases and go, okay, this is a trade-off that I can make, but that's my choice.

>> You've got such a powerful technology and it's very cool to hear you open to having these discussions. Garrett, thank you so much.

>> Thank you very much. Thank you.

[applause]

>> That was a heavy one, right? Like we're all facing this question with ubiquitous surveillance. And look, think about it. It's totally legal to film in public places, but now we have these AI enabled cameras that are tracking every single person or vehicle that drives by. And then when something goes down, you have a drone that from really high altitude can zoom in and track a suspect. Like this is insane technology that exists today. This is obviously a controversial topic and people are on different sides of this. But at TED, we want to hear arguments on both sides. Most people want to live in a world that is free from crime. At the same time, nobody wants to live in a perpetual panopticon where every move that you do is surveiled. And a lot of the double-edged nature of this technology comes down to the people that are using the tools, right? like who gets the keys to the castle and how are they deploying this technology. The best thing we can do is draw awareness to these issues and have a conversation around it because the technology is one thing but the question about how we utilize it in day-to-day society is a collective conversation. So regardless of where you fall in the issue, we want to hear from you. So let us know your thoughts. I hope you enjoyed

</details>