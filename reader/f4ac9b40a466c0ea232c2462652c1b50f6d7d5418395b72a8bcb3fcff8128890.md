---
layout: post.njk
source: https://yage.ai/share/reticulum-drone-offline-network-20260811.html
speaker: yage.ai
title: |-
  挂在无人机上的离线网络：Reticulum
  怎么把电波和协议玩出花？
date: '2026-08-11'
summary: 文章介绍了 Reticulum 这一离线网络实验，它通过将卫星、以太网和 LoRa 无线电波等多种物理链路抽象为统一的接口，并采用基于密码学身份的寻址机制，构建了一个自给自足的网络。该系统展示了在极端物理限制下，如何设计灵活的协议栈以实现跨越不同介质的可靠数据传输，并启发了在边缘 Agent 系统中实现身份与位置解耦的工程思想。
area: tech-engineering
category: ai-application
tags:
  - offline-network
  - wireless-communication
  - protocol-stack
  - identity-addressing
  - agentic-workflow
people: []
companies_orgs: []
products_models:
  - Reticulum
  - Starlink
  - Columba
media_books: []
draft: true
status: evergreen
---

在荒野里，一台关闭了蜂窝、Wi-Fi
和蓝牙的手机屏幕突然亮起，收到一条几英里外发来的短消息。这条消息的旅程相当折腾：先走
LTE 蜂窝网络发到云端，再从 Starlink
卫星落回地面网桥，转成无线电波穿过有大量植被和障碍物的地面路径。地面路径失联后，一架小型无人机吊着硬币大小的开发板升空接力，终于把数据送到了手机上。

这项工程走的是好玩的极客实验路线，不同于商业电信产品。实验的主角叫 Reticulum。它不用 IP
地址，也不管运营商是谁，硬是把卫星、以太网和微弱的 LoRa
无线电波缝在了一起，搭出了一个自给自足的网络。

## 挂在无人机上的离线网络：一场硬核的极客实验

在 Data Slayer 的测试现场，一台
LTE 联网手机要把消息送到另一台关闭蜂窝、Wi-Fi
和蓝牙的手机，消息传输路径在底层拆成了五段不同 carrier。发送端手机在
Android 上运行 Columba
客户端，数据先走 LTE 发给 GCP 上的公网 Reticulum TCP 节点，再跨越
Internet，从 Starlink 卫星链路下发到地面 Linux 网桥 Haven。Haven
上的节点通过 USB 驱动射频模块，把数据直接塞进 915 MHz 的 LoRa
无线电频段。

当车开到约 2.5 英里外时，地面 LoRa
路径失联；现场有大量植被和障碍物，但视频没有测量到足以隔离具体原因的数据。Data
Slayer 甩出一个特别酷的现场解法：他把一块几厘米见方的微型 MCU
开发板挂在小型无人机肚子里，直接飞到了树冠上方。板子刷着开源的 RTNode
路由固件，在半空中监听广播。继续升高、触发 Announce
并反复试发后，离线手机终于收到了这条跨越公网、卫星、丛林和天空的消息。

用无人机做空中中继不仅展现了无线节点在地形阻隔下的弹性，手把手搭起来的成本也很吸引人。视频作者把这块集成
ESP32-S3 与 SX1262 的 Heltec V4 称为 “a $20 transport
node”。它不需要完整操作系统，但仍需要 LoRa
radio、兼容固件、匹配的无线参数和供电；只有 ESP32
的基础开发板不能直接充当这个中继。虽然这次测试的长途段还是用了 Internet
和 Starlink，但它展示的事情非常过瘾：路径跨过了 5 段
carrier，收发两端的加密身份、应用逻辑与消息协议却不用为每一段重写。

Reticulum 消息从联网 Android 经
GCP、Starlink、Haven 和 LoRa 无人机中继抵达离线 Android 的五段 carrier
路径

## 密码学即寻址：Reticulum
是怎么做到的？

Reticulum 没走常规 TCP/IP
的路子，而是在用户态重新写了一整套独立的网络协议栈。平时上网靠 IP 地址和
DNS 域名找设备，Reticulum 在底层干脆不要 IP 了。

在 Reticulum 的世界里，找设备全靠密码学身份
Identity。每个端点或服务都会生成一套包含 X25519 加密公钥和 Ed25519
签名公钥的 Identity。把 Identity 加上应用名称与属性一起做哈希，就能算出
128 位的 Destination 地址：

destination = trunc128(SHA256(name_hash || identity_hash))

这么做直接把设备位置和身份解耦了。地址只代表具体的应用端点，管你在哪里、用什么网段、走什么介质。就算设备从局域网切到
Wi-Fi，或者从 Starlink 切到 LoRa，它的 Destination
地址始终原封不动。

找路这件事靠带有签名的 Announce 宣告在网络里广播。需要公布可达性的
inbound SINGLE Destination 会主动发送 Announce，沿途的
Transport 节点验过签名后，在路由表里记下去找这个 Destination
时下一跳该走哪个接口，然后按规则接着往外发。整个网络里没有掌握完整地图的大脑，数据包全靠下一跳指引往目的地挪。

各种不一样的介质，在这套体系下收拾得齐齐整整。Reticulum
把所有物理链路统一抽象成了 Interface。同一个 RNS 数据包，走公网时套上
TCP 报文，走串口时直接发原始字节，飞在空中就变成 LoRa 射频帧。Haven
不需要把 LXMF 消息翻译成另一种应用协议，而是根据 RNS 路径把 routing
envelope 从 TCP/Starlink 一侧转交到 LoRa 接口；无人机上的节点只在两个
LoRa hop 之间继续转发。

## 应对工程挑战：协议层怎么顶住物理限制

把网络协议扔进没有基础设施的野外，各种物理限制立刻就找上门来。Reticulum
在协议层想了不少精妙招数。

山头和树林阻挡无线信号是第一道难关。这套地面配置在约 2.5
英里处失联；无人机升到树冠以上后最终恢复了路径，但这次前后对比没有控制变量，不能把失败确定归因于山体视距。Reticulum
允许用户把运行它的实例显式配置为 Transport
Node；这个角色默认关闭，实际网络通常只让少量稳定、位置合适的节点承担转发。无人机高空接力只是个好玩的例子，固定高位节点、系留气球或其他持续供电的中继也可能提供替代路径。源码把建立
Link 的最低介质 bitrate 设为 5
bps，说明控制面考虑了极低速链路；这不等于任意弱信号下都能建链，也不代表
5 bps 足以正常聊天或传文件。

极不均匀的传输带宽是第二道难关。光纤以太网一口能吞下上千字节，LoRa
无线电的信道却窄得可怜。Reticulum 在传输层设计了三级递进： -
Packet：适合单次短消息，默认 MTU 只有 500 字节，在窄信道里保持低开销。 -
Link：两端建立带验证的双向加密会话，自动协商临时密钥，默认自带前向安全性。
- Resource：专门用来搬运图片或文件这类大块头。Resource 会在 Link
上自动分段、压缩、按顺序发完并在对面拼好。

没人管的网络里怎么保安全是第三道难关。视频所用的
SINGLE/Link LXMF
消息按协议设计端到端加密，中继正常情况下不需要 payload
key；未泄露私钥时，它也不能伪造合法发送者的签名。但 PLAIN
traffic、Announce 和部分控制或证明报文是例外，routing 与下层链路
metadata 仍可见，因此拿到中继硬件不能概括成只会看到加密乱码。

当然，极客项目和成熟的电信基础设施比起来，物理限制依然客观存在。LoRa
是低带宽、半双工的共享介质，airtime、重发和频谱规则共同限制容量，适合发发短文本和控制指令，撑不起高频实时语音；手机系统的后台休眠也偶尔会把无线连接挂断。但这完全不妨碍
Reticulum 成为一个让人眼前一亮的工程范本。

## 思想外溢：从
Reticulum 到 AI Builder 的脑洞

Reticulum
的出发点是在荒野里搭不受制于人的自组网，但它亮出来的工程思想，对每天跟模型和
API 打交道的 AI Builder 同样非常有启发。把视线从电波和开发板上挪开，把
Reticulum 的解耦哲学平移到 AI 系统里，能碰出不少好玩的方向。

Reticulum 将应用与消息、身份寻址和可替换
carrier 分层，并把控制权向上移动

### 启发 1：Agent
网络的边缘自组网与离线容灾

当前的 Agent 架构高度依赖云端控制节点和稳定的公网 API。如果把
Reticulum 的网络能力引入边缘
Agent，比如跑在树莓派、手机或车机上的小模型，Agent
之间就能在断网或局域网环境里，直接用蓝牙、Wi-Fi 甚至 LoRa
交换消息。Reticulum 可以为这些 Agent
提供离线寻址、路径发现和消息传输；应用层还需要自行定义 Tool
描述、能力匹配、调度、任务委派与结果确认，Announce 和 Transport
本身不会把这些工作自动完成。

### 启发
2：Identity 与 Location 解耦对 Durable Agent 的启发

在很多 Agent 框架里，Agent 的身份总是和部署 URL、容器 IP 或者云厂商
Client ID
绞在一起。服务器一迁移，上下文和身份经常跟着灰飞烟灭。Reticulum
这种地址跟密钥走、不跟 IP 走的设计，给长寿命 Agent
提供了特别干净的参考：Agent
的主身份密钥、任务记忆和状态连续性，应该彻底跟底层运行环境解耦。就算换了服务器甚至换了模型供应商，Agent
的加密身份和没完成的任务契约依然安然无恙。

### 启发
3：极端低带宽约束下的 Agent 协议压缩

Reticulum 逼着开发者在 500 字节的 MTU
限制里琢磨协议效率。相比之下，现在的 AI 开发习惯了挥霍 Token，JSON
报文里填满了各种冗余字段。如果要在带宽极度吃紧的信道，比如在卫星通信或者边缘设备之间，传递
Agent 的意图与决策，就得设计更紧凑的 Agent
协议。剥掉自然语言的废话，把工具调用和结构化推理压缩成紧凑的二进制
Payload，是 Agent 走向现实受限环境的必经之路。

### 启发
4：Reticulum 作为边端 AI 传感与 C2 通信总线

把端侧 AI
模型扔到野外无人机、摄像头或者边缘传感器上时，在配置好接口、无线参数、转发节点和可达路径后，Reticulum
可以承载控制与遥测消息，并为合适的 Destination 类型提供端到端加密。AI
可以在边缘节点完成感知和推理，再通过这条消息路径把高价值的极简事件摘要推回控制端。抗干扰、抗封锁和抗毁性仍取决于射频设计、冗余路径、供电与部署拓扑，协议本身不保证这些性质。