---
author: House of El - AI
date: '2026-05-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5fbhd0r3wLw
speaker: House of El - AI
tags:
  - ai-surveillance
  - privacy-governance
  - license-plate-readers
  - agile-regulation
title: 垃圾袋下的监控帝国：Flock Safety 与不可逆的公共匿名消亡
summary: 解析美国 AI 智能监控摄像头巨头 Flock Safety 的商业化扩张及其背后的社会性漏洞。文章通过分析移民执法渗透、儿童敏感区域演示、单方面合同条款修改等三大失效案例，探讨了当资本逐利逻辑、地缘政治与公共监控网络交织时，缺乏前置防线与敏捷监管所带来的数据隐私黑洞与公权力失控。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Flock Safety
  - ICE
  - 404 Media
  - Clearview AI
products_models: []
media_books: []
status: evergreen
---
### 垃圾袋下的尴尬：城市无力收回的监控特权

在美国俄亥俄州的代顿市（Dayton），一些本该全天候运转的智能监控摄像头如今却被套上了黑色的垃圾袋。这种略显荒诞的奇观并非临时维护，而是当地政府在面临巨大舆论压力与复杂的合同纠纷时，所能采取的唯一妥协方案。民选官员们在引入这些设备后尴尬地发现，他们甚至搞不清楚自己是否有权将其拆除、设备是否仍在后台静默录制，以及如何合法地解除与监控设备供应商签订的约束性合同。最终，派遣警察和市政工人用黑色塑料袋套住摄像头，成了他们应对公权力及隐私争议的“最终解决方案”。

同样的尴尬也在伊利诺伊州的埃文斯顿市（Evanston）上演。该市在单方面终止与同一家公司的合同后，对方却在未获得许可的情况下重新安装了摄像头。为了在漫长的司法诉讼期间维持秩序，埃文斯顿市也只能将这些摄像头套上垃圾袋，并向该企业发送了停止侵权函。这两个截然不同的城市，在面对不受控制的现代化监控设施时，却不约而同地走向了同一个终点——用最原始的垃圾袋来遮蔽最前沿的 AI 科技。

这些被垃圾袋封印的设备属于一家名为 **Flock Safety** 的美国监控巨头。

<details>
<summary>Original English</summary>

You were identifiable at every single one of these points and you didn't opt into any of them. Right now in Dayton, Ohio, there are AI-powered surveillance cameras on public streets that are covered in black bin bags because the city government, the actual elected officials responsible for public safety, cannot figure out whether they are allowed to take the cameras down, whether the cameras are even still recording, or how to get out of the contract they signed with the company that installed them. Their solution was to send the police department and the public works team out with bin liners, not as a temporary measure while they figured out the real solution. That was the solution, which to be fair is also my solution when something in the fridge has gone wrong and I don't really want to investigate further.

In Evanston, Illinois, the city terminated its contract with the same company. The company then reinstalled the cameras without permission. That is a level of persistence usually reserved for exes and browser toolbars. The city had to send a cease and desist letter and then, while they waited for the legal process to play out, they also covered the cameras in bin bags. Two different cities, same conclusion, bin bags. These cameras belong to a company called Flock Safety.

</details>

---

### 资本扩张与全国联防：无凭证的跨州数据穿透

成立于 2017 年的 Flock Safety 起源于一个典型硅谷式的痛点故事：创始人遭遇了财产盗窃，却因缺乏证据而使警方束手无策，于是他研发了一款以太阳能为动力、可自动识别车牌并上传云端的数据相机。对于饱受汽车盗窃、人口失踪以及恶性犯罪困扰的小型社区而言，以每台相机每年 2500 美元的价格提供免维护的“监控即服务”（Surveillance as a Service）无疑具有极高的性价比。这也让 Flock 获得了包括 Andreessen Horowitz、Founders Fund、Tiger Global、Kleiner Perkins 以及 Y Combinator 在内的顶级风投的青睐。截至 2026 年 4 月，该公司估值已飙升至 84 亿美元，其网络连接了全美超过 5000 家执法机构。

然而，Flock 真正的商业护城河不仅在于硬件的普及，更在于其网络效应：它将数万台分布在全美各地的摄像头织成了一张全国性的共享网络。这意味着，佐治亚州的警局可以在未经法庭搜查令（Search warrant: 司法机关授权搜查的法律文书）或传票的情况下，直接调取并检索德克萨斯州某所学校周边的监控数据；印第安纳州的警长办公室亦可随意查看伊利诺伊州某小镇停车场的录像。在这个默认允许最大化共享的架构设计下，信息流转没有任何实质性的行政阻碍或跨州监管，用户或市民作为数据主体，对自己出行轨迹的去向完全处于信息脱节状态。这与 2010 年代初 Facebook 允许第三方应用过度获取用户及其社交关系网数据的逻辑如出一辙，最终在爆发出系统性隐私灾难之前，公众对其数据黑洞几乎一无所知。

<details>
<summary>Original English</summary>

There are over 90,000 of them across the United States. They scan 20 billion license plates every single month, which for context is more than the number of registered vehicles in the country, meaning some of you are being scanned multiple times a day and the most exciting thing you did was maybe go to Costco. An growing number of cities are slowly discovering that the surveillance infrastructure they invited in is far harder to get rid of than it was to install. My name is Ella. I have a PhD in computer science and I analyze AI developments to understand what's actually happening beneath all of this hype. In this video, I'm going to explain what Flock Safety is and how it ended up in thousands of cities. Then I'm going to walk through three specific ways the system has already been misused. And after that, I want to talk about something broader, why anonymity in public space is essentially already gone, why most people don't realize it, including in this audience, and what that means for how quickly regulation needs to catch up. Spoiler, not quickly enough, but you probably guessed that from the bin bags.

Flock Safety was founded back in 2017 in Atlanta. The origin story is very clear. The founder experienced a property crime. The police couldn't help because there was no evidence. So, he built a solar-powered camera that reads license plates automatically and uploads the data to the cloud. Simple, definitely useful. The kind of technology that genuinely does help recover stolen vehicles, find missing persons, and track suspects in violent crime cases. Nobody serious really is arguing that the core technology has no value. Somebody gets their car stolen, the camera catches the plate, the police recover it, great. The problem is that nobody has ever raised a billion dollars to just stop at great. The pitch to cities was of course straightforward. For $2,500 a year per camera, Flock would install, maintain, and operate the hardware. The city got access to a software platform with real-time alerts and searchable footage. So, no upfront capital expenditure, no specialist IT staff required. It was surveillance as a service. And for a small city with a limited budget, it looked like an extraordinary deal. And in the same way that the first month of any subscription is an extraordinary deal, the complications arrive later. And the venture capital market agreed. Flock has raised over $1 billion in total funding. Its backers include Andreessen Horowitz, Founders Fund, Tiger Global, Kleiner Perkins, and Y Combinator. So, the usual people who show up when something is either going to change the world or get investigated by Congress, often both. As of April 2026, the company was valued at $8.4 billion. Its annual recurring revenue crossed $300 million in 2025, representing 70% year-over-year growth. More than 5,000 law enforcement agencies and 4,800 police departments are connected to its network. That network is the critical architecture detail. Flock doesn't just sell cameras to individual cities, it connects them into a national system where any participating agency can search any other agency's camera data. A police department in Georgia can run a plate against cameras at a school in Texas. A sheriff's office in Indiana can search parking lot footage from a suburb in Illinois. No warrant needed, no subpoena, no notification to the city that owns the camera, no particular reason needed, frankly. The network effect is precisely what makes Flock attractive to investors. It is also precisely what should make everyone else nervous.

And there is a historical parallel here that I think is worth sitting with for a second. In the early 2010s, Facebook data sharing defaults kept quietly expanding. Third-party apps could access not just your data, but your friends' data. The platform setting were technically configurable, but the defaults favored maximum sharing because maximum sharing was maximum growth. Most users had no idea how broadly their information was being distributed until Cambridge Analytica made it impossible to ignore. By then, the data was already out, which is the tech industry's version of we've already eaten the cake, but we'd love your thoughts on the recipe, please. The architecture had been doing its work for years before anyone with the authority to stop it understood what was actually happening. Flock's national camera network operates on a structurally identical logic to this. The default is sharing, the value is in the network, and the people whose data flows through it have very little visibility into where it goes. If you've been following this channel, this pattern might feel familiar. I recently covered surveillance pricing in a video essay that I will link below. That's on the practice of using AI to charge different customers different prices based on their own personal data. That one was deployment of AI-powered monitoring going sideways. This is another case. The connecting thread between these stories is not the specific technology, it's the deployment itself. AI is powerful and in many cases it is generally useful, but the incentive to deploy it in ways that expand surveillance keeps winning because expanding surveillance is where the money is. And when the financial incentive and the surveillance capability point in the same direction, the question is not whether somebody will abuse it, the question is just how quickly.

</details>

---

### 系统性失效的三个维度：商业与伦理防线的坍塌

当庞大的监控公权力缺乏物理与法律层面的隔离时，系统滥用便呈现出不可阻挡的必然性：

* **第一维：越界的“后门”移民执法**。尽管 Flock 官方多次声明其没有与美国移民和海关执法局（ICE）开展直接合作，但实际上由于 4800 个共享终端之间缺乏审计机制，部分与 ICE 签署了联合协查协议的地方警局，在没有联邦授权的情况下频繁为 ICE 充当数据掮客。经媒体与人权组织核实，已有超过 4000 次车牌检索是通过这种所谓的“侧门”方式，调用包括 100 多个公立学区周边摄像头在内的设备，专门用于追踪和拘留移民。
* **第二维：违背职业操守的商业演示**。在亚特兰大郊区的邓伍迪（Dunwoody），居民通过信息公开申请查阅了 Flock 系统的访问日志，震惊地发现该公司高管和销售人员为了向其他城市的警局推销产品，曾多次随意登录正在运行的真实监控系统进行功能演示。演示画面甚至包括马库斯犹太社区中心游泳池、游乐场以及儿童体操房的实时影像。尽管 CEO 事后就此公开道歉，但随后邓伍迪市政议会依然在抗议声中续签了合同。
* **第三维：单方面更改的数据协议与退网陷阱**。在积累了绝对的市场优势后，Flock 于 2026 年 2 月悄然删除了其长期标榜的“Flock 不拥有、亦绝不出售客户数据”的合规承诺，转而规定该公司拥有使用和披露所有客户数据的“永久、不可撤销授权”。这让那些试图终止合同的城市面临极高壁垒——正如尤金市（Eugene）等地方所遭遇的那样，不仅面临被监控服务商单方面断联的风险，甚至不得不自费派遣市政工人登梯手动拆除摄像头，以对抗迟缓的硬件退出流程。

这说明，即便是打着公共安全旗号的 AI 基础设施，其运行轨迹最终也是被能带来最多财富或最高统治权力的资本力量所裹挟，而不是公共利益。

<details>
<summary>Original English</summary>

So, what went wrong? Well, three things and each one reveals a different dimension of the same structural problem. The first is immigration enforcement. Flock's own website states clearly, "Flock does not work with US Immigration and Customs Enforcement ICE." The company does not partner with ICE. ICE does not have direct access to Flock camera systems or data. That is technically true. Flock did not hand data to ICE. What Flock built was a system where 4,800 police departments can search each other's cameras with functionally zero oversight and some of those departments have agreements that turn local officers into immigration agents. The result documented by 404 Media, the University of Washington Center for Human Rights, and The 74 is that local law enforcement officers have been running Flock searches on behalf of ICE, so-called side door access. Over 4,000 lookups have been conducted at the behest of the federal government for immigration purposes. School cameras installed in over 100 public school systems are part of the searchable network. Dayton Ohio was sharing Flock data for immigration enforcement apparently by accident, which is the phrase that should never appear in the same sentence as immigration enforcement, and yet here we are. Flock does not work with ICE is doing a lot of work there. Flock built a highway. It is not responsible who drives on it. That distinction is, I suspect, more comforting to Flock's legal team than it is to the communities being surveilled.

The second failure is the Dunwoody incident. Dunwoody is a suburb of Atlanta where Flock operates a comprehensive surveillance system, including a real-time crime center powered by Flock Safety. A local resident named Jason Huynh filed a public records request and obtained the access logs. What he found was that Flock employees had been logging into Dunwoody's camera system to run live sales demonstrations for police departments in other cities. The cameras they chose to demo included feeds inside the Marcus Jewish Community Center of Atlanta, specifically cameras pointed at the children's gymnastics room, the pool, and the playground. A Flock vice president accessed the gymnastics camera. Another employee accessed cameras labeled Jim Mandel 1 and Main Pool Right. Flock's website states that nobody from Flock Safety is accessing or monitoring your footage. The CEO personally apologized to the community center and promised radical transparency. That is a bit like a locksmith who got caught letting himself into your house promising to be more transparent about his key collection. Residents packed city council meetings for nearly 3 hours of public protest. The city renewed the contract anyway. So, 3 hours of public fury followed by the council presumably just shrug and basically saying, "But the price was really good."

The third failure is in the contract trap itself. In February 2026, Flock rewrote its terms and conditions. The new terms had granted the company a perpetual irrevocable license to use and disclose all customer data. The previous version had explicitly stated the following, "Flock does not own and shall not sell customer data." That promise was deleted. Flock called the removal redundant in the same way that removing the locks from your front door could be called redundant if you already trust everyone on your street. As one resident who read the full contract noted, no replacement language exists anywhere. And meanwhile, Flock's marketing website still promises that your neighborhood owns 100% of the data, and Flock Safety will never share, sell, or access your data, which means either the marketing team and the legal team are not speaking, or they are and this is just the result. Cities that want out are discovering that leaving is not exactly simple. Contract terms are unclear on whether cities can unilaterally deactivate the cameras. In Evanston, the city terminated its contract and Flock reinstalled the cameras without the city's permission, leading to a cease and desist. In Eugene, Oregon, the city terminated its contract and requested Flock remove the cameras by December 12th. Flock told them it would not begin removal until January 26th. The city sent its own staff out to physically take the cameras down. The city literally sent casual workers out with ladders. This is literally what happens when your surveillance vendor ghosts your breakup texts. More than 40 cities have now suspended or terminated Flock contracts, including Mountain View, Cambridge, Santa Cruz, and Boston. Many more are debating it. And through all of this, the I saw the access, the children's gymnastics footage, the contract rewrites, the reinstated cameras, the 40 cities pulling out, Flock's valuation went from $3.5 billion to $8.4 billion. The market is rewarding the behavior that communities are protesting. That is not a bug. That is the incentive structure working exactly as designed.

</details>

---

### “我用现金支付”的盲区：多维特征识别与后摄政时代的到来

在隐私讨论中，常能看到网民留下“我用现金支付”、“我把手机放进屏蔽袋”或“我出门用代理 VPN”等应对策略。然而，这种依靠控制个人设备的防范思维，已经落后了当前技术形态整整十代。如今的 AI 智能系统已经彻底摆脱了对个体设备和传统 ID 的依赖。

以车辆为例，Flock 内置的 **车辆指纹**（Vehicle fingerprint: 结合物理瑕疵、非标准配件等多维度视觉特征识别物体的算法技术）不仅能够识别车牌，还会提取车型、颜色、车尾贴纸、自行车架、划痕甚至是保险杠的凹陷细节。因此，即使你把手机封锁在 Faraday 屏蔽袋中并使用现金消费，你驾驶的载具也早已在出发地到目的地的数十个沿途节点被录入、识别并做好了精确的时间标记。

车辆仅是泛在监控图景中的一个切片。当我们在现代都市穿行时，在完全没有主动授权（Opt-in）的场景下，大量被动识别早已将我们合围：
* 门口的 CCTV 配合 AI 动态面部追踪实时锁定行踪轨迹；
* 支付终端的刷卡记录绑定了交易详情与物理空间坐标；
* 居民楼上的智能门铃和随处可见的交通测速仪默默记录着每一帧影像；
* 类似 Clearview AI 这样的商业机构已经从互联网公开渠道非法抓取了超过 600 亿张面部生物信息，以商业数据库的形式将警务检索权贩卖给美国海关等联邦机构。

这些碎片化的单一视图经过后台算法整合，拼凑出的是关于你何时、何地甚至因何出行的完整画像。在当前的现代城市中，除了远离人烟的荒野和海洋，已不存在任何真正的隐私盲区。

<details>
<summary>Original English</summary>

By the way, if you'd like to support this work and help keep it free and without any gatekeeping, you can do that via coffee or channel memberships. The links are down below. And now I want to zoom out because Flock is a case study, but the pattern is bigger than just one company, and it connects to something I think most people fundamentally underestimate how much of their public life is already being recorded, identified, and stored. When stories like this break on this channel, the comment section usually fills up with a certain kind of response. I'll just pay in cash. I'll put my phone in a Faraday cage. I'll just use a VPN. And I understand the impulse, and it's not necessarily incorrect, but it reflects a model of surveillance that is about a decade out of date. The idea that if you control your device, you control your visibility. Flock's cameras don't need your phone. They don't need your name. They build what the company calls a vehicle fingerprint, not just the license plate, but the make, model, color, bumper stickers, bike rack, dents, scratches, stuff like that. Pay cash at the shop if you like. The car you drove there has already been logged, matched, and timestamped across every Flock camera between your home and the parking lot. You were identified before you opened your wallet.

And vehicles are just only one layer. Think about how many identification systems you pass through in a single day without noticing. You walk into a shop, the CCTV above the entrance is no longer just recording grainy footage to a VHS tape in a back room. Increasingly, it is connected to AI-powered platforms that can match faces, track movement patterns, and flag individuals in real time. You tap your card or your phone at the register, that transaction is logged with your name, the time, the location, and what you bought. You walk past a building with a smart doorbell camera, that footage is searchable. You get on public transport, more cameras. You drive through a junction, Flock or one of its competitors captures your vehicle fingerprint. You enter your workplace, access badge logged. You were identifiable at every single one of these points, and you didn't opt into any of them. Facial recognition databases already exist within government systems. Your passport photo, your driving license photo, your visa application, that biometric data sits in databases that law enforcement agencies can and do access, and it does not stop at government. Clearview AI, a separate company, has scraped over 60 billion images from the public internet to build a facial recognition database that law enforcement agencies pay to access. US Customs and Border Protection signed a contract with them. The layer stack as well, license plate readers, facial recognition, transaction records, phone location data, building access logs, smart home devices, each one is just a partial view, but combined, they are a comprehensive record of where you were, when, and often why. You would need to avoid every camera in every public space you enter, which in a modern city is functionally impossible. The only genuine dead zones are deep wilderness and the open ocean, and even there, if you brought your phone, you're identifiable anyway. Now, I'm not saying this to fearmonger, by the way, most of real life is still very normal. Nobody is being hunted through the streets by an algorithm on a Tuesday afternoon, but the infrastructure exists, the data exists, and the point of analyzing these things properly, which is what this channel is about, is to think through what happens when the incentives align for that infrastructure to be used in ways nobody's stress tested. Because we have already seen that happen. Flock's Network was built for stolen cars and missing persons. It is now being used for immigration enforcement, sales demonstrations involving children, and data sharing under terms that were rewritten after cities signed up.

</details>

---

### 规则重构的滞后性：呼唤“敏捷监管”抗衡技术野蛮生长

为什么科技治理总是显得如此苍白无力？从立法学角度来看，绝大多数规章制度都具有“滞后反馈”特征。例如阿拉巴马州明文禁止“人熊摔跤”、伊利诺伊州规定携带价值 300 美元以上的 salamander（蝾螈）属于重罪，以及禁止在公共节日过后乱丢彩色拉炮碎屑等规定，都是在有具体损害发生并引发社会乱局后，立法机关才不得不被迫进行的反应性（Reactive）补救。

同理，目前尚无任何联邦法案阻止第三方监控企业将民居周边的实时视频用于商业路演，也没有明确法规限制由 90,000 台摄像头构成的跨部门信息穿透深度，更没有强制赋予地方社区对于买断设备的绝对物理断网控制权。在数据和资本以光速裂变的今天，等待灾难显现再进行冗长听证的传统监管模式已然宣告失灵。

从计算机科学的角度来说，解决此类敏感数据穿透的手段并非不存在。在学术界中，**差分隐私**（Differential Privacy: 一种通过添加噪声防止个体隐私泄露的算法框架）与 **联邦学习**（Federated Learning: 分布式机器学习方法，数据不出本地即可完成联合建模）等技术本可以从架构设计层面（Privacy by Design）彻底避免跨州数据滥用或销售侧门接入。然而，在缺乏强制性合规要求的市场环境下，商业利益驱动着技术公司直接略过安全护栏以追求极速扩张。

如果不想让套在摄像头上的黑色垃圾袋成为后监控时代最具讽刺意味的治理图腾，我们就必须推动类似于软件工程迭代机制的**敏捷监管**（Agile Regulation: 随技术环境动态演进并具备前置模拟测试的弹性治理模式），在技术和场景被大规模部署之前，对失效边界进行前置的红队压力测试。

<details>
<summary>Original English</summary>

The technology itself, AI, is neutral, like fire or electricity. It can be used for extraordinary good, but deployment without guardrails means the use case that emerges is the one that makes the most money or serves the most power, not the one that serves the public interest necessarily. And in a competitive economic environment where someone has to choose between making the world slightly worse or making money, some people will just choose the money. I'll avoid the C-word here, not because I'm afraid of it, but because it tends to make the comment section lose its collective mind, and I need you guys focused for this one. But, increasingly, a lot of people, when pressed, will simply choose to make the world slightly worse if it means they can survive. And as economic pressure tightens further, more people get pushed towards that choice. It only takes one or two. One employee pulling up a gymnastics room feed for a sales demo, one local officer running a plate search on behalf of a federal agency, the system doesn't need to fail catastrophically, it just needs to fail in the small, predictable ways that nobody bothered to prevent.

This brings me to regulation, and this is a point I think about a lot. Have you ever looked at a law and just thought, "Why does this exist? Who would ever do that?" In Alabama, there is a law explicitly banning bear wrestling, not because Alabama legislators woke up one morning worried about theoretical bear combat, but because people were actually training bears to fight and surgically altering them to be better wrestlers. In Illinois, it is a felony to possess more than $300 worth of salamanders, which raises the immediate question of how anyone arrives at exactly $300 worth of salamanders and what they were planning to do with them. In Mobile, Alabama, it is illegal to possess prey string, and you can picture exactly the kind of festival cleanup disaster that prompted that one. Every one of these laws sounds absurd until you realize the law exists because somebody already did the thing. That is how regulation works. It is inherently reactive. Somebody does something nobody anticipated, and then the rule gets written. Right now, there is no law that prevents a surveillance company from using live footage of children's gymnastics classes as a sales demonstration. There is no federal regulation governing how data from a national network of 90,000 AI-powered cameras gets shared between agencies. There is no requirement that cities be able to unilaterally deactivate surveillance hardware they are paying for. These rules do not exist because until very recently, nobody imagined they would need to. The problem is that AI deployment moves at venture capital speed and regulation moves at committee speed. By the time the bin bag goes over the camera, the data has already been shared with 4,800 agencies, the contract terms have already been rewritten, the valuation has already been doubled. The reactive model of regulation, wait for the damage then legislate, cannot keep pace with technology that scales this fast.

Privacy and computer science is a massive field. The researchers I met during my PhD had methods so sophisticated that even I, as somebody with a doctorate in the discipline, found them very non-trivial. The expertise exists, the methods exist, differential privacy, federated learning, access control architectures that would make side or search a structurally impossible. The technical solutions to these problems are not hypothetical. They are just not being required. I'm not saying that we can write perfect regulation, by the way. The field of law is complex because humans are complex, but the current approach, deploy first, discover the misuse later, spend months in city council meetings debating whether you're allowed to remove the hardware, this is not good enough. What is needed is something closer to how software itself gets built. Iterative, adaptive, tested against failure modes before deployment, not after. Think of it as agile regulation. It sounds like a contradiction, I know, but it is the only model that has any hope of keeping pace because right now the bin bag is the most ominous symbol I've seen in technology governance in years. It is the government that bought a surveillance system it didn't fully understand, discovered it was being used in ways nobody anticipated, and responded with the only tool it had available. Not a policy, not an injunction, not a technical safeguard, a bin bag placed carefully over a camera that may or may不定 still be recording, installed by a company that may or may not honor a termination notice, feeding data into a network that no single city controls. That is what happens when the speed of deployment outpaces the speed of oversight. You don't get solutions, you don't get regulation, you get a bin bag and a hope that nobody checks whether the camera is still on or not. But surveillance cameras tracking where you drive are only one layer of how AI is being used to watch you. What happens when the same logic gets applied to what you buy and companies start charging you different prices based on your personal data? The results are about as reassuring as a bin bag over a camera. That's the video that I would watch next. Thanks so much for watching this one. Subscribe and I'll see you all on the next one.

</details>