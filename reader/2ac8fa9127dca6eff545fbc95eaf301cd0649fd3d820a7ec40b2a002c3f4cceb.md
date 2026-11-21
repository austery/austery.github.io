---
layout: post.njk
source: https://yage.ai/share/api-key-where-20260511.html
speaker: yage.ai
title: API key 到底放在哪儿？——两个最常见场景的入门指南
date: '2026-05-11'
summary: 本文探讨了API密钥在个人开发机器和生产服务器两种场景下的存储安全问题，强调了理解威胁模型的重要性。针对个人机器，推荐FileVault、macOS Keychain或配置权限的.env文件；针对生产环境，则建议使用systemd credentials或集中式密钥管理方案，并反对使用环境变量。文章指出，密钥轮换频率对安全性影响比存储方式更大，并提供了简化的决策指南。
area: tech-engineering
category: software-development
tags:
  - api-keys
  - secrets-management
  - security-best-practices
  - development-environments
people: []
companies_orgs:
  - 1Password
  - OpenAI
  - Tavily
  - CNCF
  - OWASP
  - HashiCorp
  - Infisical
  - Nginx
products_models:
  - .env
  - FileVault
  - macOS Keychain
  - systemd credentials
  - 1Password Service Account token
  - HashiCorp Vault
  - Infisical
  - TPM2
media_books: []
draft: true
status: evergreen
---

你刚拿到一个 API key。OpenAI 的、Tavily
的、或者某个第三方服务的。你的代码需要它才能跑，你的 AI
助手也需要它才能替你调接口。

犹豫了几秒之后，你把它放进了 .env
文件。这和所有人刚入行时做的一样，是一个默认的、几乎不需要思考的选择。

但之后你会开始不安。听说 .env 不安全。听说应该用
1Password、或者
Vault、或者什么别的。你搜了一圈，看到一堆文章告诉你”不要把密钥放
.env
里”，但它们很少说清楚：那到底放哪儿？更少有人说清楚：在你的具体情况下，放哪儿才是对的。

这篇文章想把这件事拆开。不列工具清单，不推任何产品，只讨论两种最常见场景下，你面对的真实威胁是什么，以及针对每一种威胁怎么做才算够。

## 先搞清楚你在防什么

密钥安全不是一条纵轴，从”不安全”到”安全”排着走。它是一个二维问题：不同场景对应不同的威胁，而每种做法在特定威胁下的表现完全不同。

你一个人在自己 MacBook
上写代码，和你把服务部署到一台互联网能访问的服务器上，这两种情况要防范的事情几乎没有交集。把它们的密钥管理方案混在一起讨论，是大多数建议失效的原因。

个人机器上，你真正要防的东西其实不多。机器在你家里或书桌上，只有一个登录账户，没有其他用户在上面跑进程。坏人要拿到你机器上的
API key，需要过三道关：物理盗窃、远程入侵、或者不小心把它提交到了 Git
仓库。

第一道，macOS 自带的
FileVault（全盘加密功能，在系统设置里就能打开）已经替你挡掉了：关机后磁盘内容无法被读取，偷走机器的人看不到你的任何文件。第二道对个人机器来说概率很低——你没有暴露在公网的端口，没有陌生用户在你的系统上跑命令。第三道是真实风险，但它是操作习惯问题，不是工具选择问题。

CNCF
的 Cloud Native Security Whitepaper 说 secrets
应该”通过非持久化机制在运行时注入”，OWASP
的 Secrets Management Cheat Sheet
说”不推荐使用环境变量，除非其他方法不可行”。这些标准针对的是多租户生产环境——多用户共享同一台机器、进程间可以互看对方的环境变量（Linux
下 /proc
目录允许同用户的其他进程读取你程序的启动参数和环境变量）、日志和程序崩溃时的调试文件会被集中收集。你的个人机器不属于这个范畴。你和
root
之间没有信任边界，任何能读写你文件的进程本来就能做更多破坏性的事。在这个
threat model 下，.env 带来的额外暴露面并不大。

生产服务器上，威胁模型完全不同。互联网暴露面意味着任何代码漏洞都可能成为入口。同一个服务器上可能跑着不同来源的服务，彼此之间应该有隔离。日志会被收集和分析，程序崩溃时的调试文件可能被第三方工具读取。环境中多了一层”恶意进程”的可能性——不是你自己的代码，而是某个被攻破的依赖、一个漏洞容器、或者一个被社工获取的
shell。在这种环境下，Linux
下同一个用户的所有进程都能互看环境变量这件事，就不再是”自己看自己”，而是一个真实的横向移动通道。CNCF
和 OWASP 的建议在这个场景下不是过度防守，是合理的基本要求。

## 场景一：你自己的机器

先说你大概率面对的这种情况。你是唯一用户，机器上开了 FileVault（macOS
的全盘加密），或者装了 Linux 的话开了 LUKS（Linux 上和 FileVault
类似的磁盘加密机制），你的代码和服务都跑在你自己的账号下。你需要的是：服务能在无人值守时启动、你的
AI 助手能读到 API key 调用接口、并且你不会因为一次不小心把
.env 提交到 Git 而把 key 送出去。

这个场景下你有四种主要选择。按多数人最可能用上的顺序来介绍。

1Password 交互式批准（op run）。
这种模式下你的电脑上不存放任何 API key——每次需要时，1Password 弹出 Touch
ID 或 Apple Watch 确认，你点一下，key
注入到当前进程。日常坐在电脑前工作时体验非常好，批准只需要半秒钟。它的根本好处是没有一个凭证持久化存在磁盘上，这也是所有方案里安全性最好的。

但限制也很明确：人不在机器旁边时弹窗没人点，服务就卡住了。所以远程
SSH、手机操作、后台服务自动启动这些场景走不通。只要你的使用模式是”自己坐在笔记本电脑前敲代码”，它是首选。

macOS Keychain（Linux 对应是 Gnome Keyring /
secret-tool）。 macOS
有一个内置的密码和凭证管理系统，叫 Keychain（钥匙串访问）。你平时看到
Safari 帮你自动填的密码，就是存在 Keychain
里的。它的工作原理是：所有存进去的数据用你登录密码派生出的密钥加密，比
FileVault 多一层保护——即使有人绕过 FileVault 读到了磁盘文件，Keychain
里的数据也不能直接解密。用命令行工具 security
可以读写它：

```
<code class="sourceCode bash"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="co"># 存一次</span></span>
<span id="cb1-2"><a href="#cb1-2" aria-hidden="true" tabindex="-1"></a><span class="ex">security</span> add-generic-password <span class="at">-s</span> <span class="st">"opencode-tavily"</span> <span class="at">-w</span> <span class="st">"sk-xxx"</span> <span class="at">-A</span></span>
<span id="cb1-3"><a href="#cb1-3" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1-4"><a href="#cb1-4" aria-hidden="true" tabindex="-1"></a><span class="co"># 服务启动时读</span></span>
<span id="cb1-5"><a href="#cb1-5" aria-hidden="true" tabindex="-1"></a><span class="bu">export</span> <span class="va">TAVILY_API_KEY</span><span class="op">=</span><span class="va">$(</span><span class="ex">security</span> find-generic-password <span class="at">-s</span> <span class="st">"opencode-tavily"</span> <span class="at">-w</span><span class="va">)</span></span></code>
```

-A 标志让所有应用可以无弹窗读取——这对无人值守的 AI
服务很关键。Keychain
在用户登录时自动解锁，后面的访问不需要交互。它解决了 .env
在备份中明文泄露的问题，同时没有引入额外的长期有效凭证。

.env 文件，权限 600。
这是基线。把它放在你的项目目录或 home 目录下，设成仅你可读写。FileVault
保证关机状态下磁盘不可读。真正常见的风险是两个操作层面的：忘了加
.gitignore 导致提交进仓库；Time Machine 或 iCloud
备份里出现了明文 key。一个简单的缓解做法是，把 .env 放回你
home 目录下的一个统一位置（比如
~/.config/keys/），然后在各项目里用软链或相对路径引用，这样你只需要记得
exclude 一个地方就行。

1Password Service Account token。 把 API key
集中存在 1Password 里，你的服务启动时用 op read 拉取。SA
token（service account token，相当于 1Password
给你的”机器身份证”）本身是一个持久的、能解锁 vault 里所有 key
的凭证，它需要放在某个地方才能让服务在无人值守时读到——换句话说，它仍然是一个落盘的”解锁钥匙”。把它放
Keychain
里（参考上面的方式）可以缓解落盘明文的问题，但不能改变一个事实：如果这个
token 被拿到，攻击者可以直接把整个 vault 里的 key 全部拉下来。

那 1Password 在这个场景下还有没有好处？有的——当你的 API key
需要轮换时。如果你有十个 key 分散在五个服务的 .env
里，换一个 key 需要逐个找到、修改、重启。用 1Password 的话只在 1Password
里换一次，重启服务就好。轮换成本的降低是实质性的安全改善，因为它让”我该轮换了”这件事更容易真的发生。

### 推荐

你的实际使用模式，决定了最适合的方案。

如果你大多数时候坐在电脑前面工作（比如一台工作笔记本，你人在机器旁边），1Password
交互式批准是最好的起点：没有持久化凭证，每次点一下 Touch ID
就行，安全性和便利性都很好。不需要加任何复杂的配置。

如果你的机器需要无人值守——后台跑服务、或者你在外面用手机远程操作家里的机器，交互式批准就走不通了。这种情况下的选择：

如果没有太多轮换需求，只是想让服务自动跑起来，.env 配合 FileVault 就可以。它是基线方案，对个人单用户机器来说够用。

如果你想让 key 不在备份和文件系统里直接明文存在，macOS Keychain 是多一层保护但不需要多安装一个服务。服务启动时自动从 Keychain 拉取，不需要交互。

如果你已经开始觉得”换 key 好麻烦”——多个服务共享同一批 API key，每次轮换要翻好几个 .env 文件，SA token 方案的集中管理优势就体现出来了。把它放 Keychain 里以减少 token 本身明文落盘的时间窗口。

## 场景二：你在跑一个生产服务

对很多人来说，这个”生产服务”其实就是一个 VPS（你在云厂商租的一台远程
Linux 服务器），上面跑着几个 side project，用 systemd 管理服务（systemd
是 Linux 系统自带的管家程序，负责启动、监控和重启你的后台服务），通过
Nginx
对外暴露。它不算什么”企业级基础设施”，但它的威胁模型和个人机器已经有本质区别。

互联网暴露意味着你的服务可能被扫描、被 fuzz、被找到漏洞。历史上不少
VPS
被攻破不是因为自己的代码出问题，而是运行了某个有已知安全漏洞的开源组件（软件行业用
CVE 编号来登记和追踪这类公开漏洞）。一旦有人在你的服务器上拿到了一个
shell，cat .env 就是成本最低的下一步。

这个场景下你要做到三件事：API key 不应该能从环境变量里直接读到（防
Linux
进程间互看、防日志泄露）、服务启动时不需要你人在场、轮换的成本要低到你能经常做。

.env 不要再用了。 这是 CNCF 和 OWASP
明确反对的。环境变量会在程序崩溃时的调试文件中出现、会被子进程继承、会通过
ps auxe
命令（显示所有进程的完整环境变量）被同机器的任何用户看到。在生产服务器上，这些不是理论风险。

systemd credentials。 systemd
除了管服务启停之外，还内置了一个密钥管理功能（从 systemd 247
版本开始就有）。你把 API key 用一行命令加密存到一个特定目录下，在
service unit 里声明加载：

```
<code class="sourceCode ini"><span id="cb2-1"><a href="#cb2-1" aria-hidden="true" tabindex="-1"></a><span class="kw">[Service]</span></span>
<span id="cb2-2"><a href="#cb2-2" aria-hidden="true" tabindex="-1"></a><span class="dt">LoadCredentialEncrypted</span><span class="ot">=</span><span class="st">api-key:/etc/credstore/myapp.api-key</span></span></code>
```

systemd
在服务启动时解密，放到一个只有该服务进程能读的临时目录里（$CREDENTIALS_DIRECTORY），服务停止时自动清除。解密密钥可以绑定到
TPM2
芯片上（主板上的一个安全芯片，很多近几年的电脑和服务器都有），让加密文件在别的机器上无法解密——即使硬盘被拔走装到另一台机器上，数据也读不了。整个过程不需要额外安装任何软件，只要你的
Linux 版本不太老，系统自带的 systemd 就能做这件事。

比起 .env，它消除了环境变量可见性问题。比起”装一个
Vault”，它没有新增依赖和运维负担。

1Password Service Account token。
逻辑和个人机器一样——在你的 ExecStartPre 或启动脚本里
op read 拉取密钥。SA token 本身仍然是一个落盘的单点，但配合
Keychain 或 systemd credentials 存放 token
本身可以收窄暴露面。集中管理带来的轮换便利在这个场景下更加实在，因为生产密钥泄露的后果比个人机器严重得多。

HashiCorp Vault、Infisical、云厂商的 Secrets
Manager。
给你完整的密钥生命周期管理：动态密钥、自动轮换、审计日志。代价是它们都是需要你认真运维的服务。对五个人以下的团队来说，Vault
的维护成本往往超过它带来的安全改善。如果你是个人跑一个 VPS，让 systemd
做这件事已经比现状好了一个数量级。

### 推荐

小规模生产部署（几个服务、一个或少数几个人维护）：Linux 上用 systemd
credentials，macOS 上用
Keychain。把密钥加密落盘、服务启动时解密注入、不进入环境变量——这条路安全收益大、基础设施变化小。如果你的密钥数量开始接近十个以上、或者需要几个人同时管理，才开始考虑
Infisical 或 1Password 做集中管理。Vault
留给已经有了平台工程团队的组织。

## 轮换频率比存储方式重要得多

不管你选了什么方案，一个没有被提到的变量才是实际影响最大的：你多久换一次
key？

传统 .env 的轮换流程很痛苦——找到 key
在哪几个文件里，逐一更新，重启所有服务，祈祷没漏。这个痛苦让大部分人选择不轮换。而密钥安全的实际差异，在”一年换一次”和”三个月换一次”之间，比在”.env”和”Keychain”之间大得多。

集中式密钥管理的真正改善不在于那个 vault
本身的密码学设计，在于它把轮换从”找文件改文件重启”变成了”在一个地方改一次，重启”。轮换成本降了三个数量级，轮换行为从”想起来才做”变成了”可以定期做”。

一个简单的自检：在你的当前方案下，如果你怀疑某个 API key
泄露了，你能在多长时间内把它换成新的？答案是小时级的，你的方案就是有效的。答案是”可能要花一下午”的，问题就不在你用的是什么工具，而在你的轮换流程本身就阻止了安全行为的发生。

## 一个极简的决策清单

走到这里，不再需要看工具对比表了。问自己三个问题就够了：

你是不是这台机器上的唯一用户？
如果是，且机器上没有跑着你不知道来源的代码，.env 或
Keychain 就够了。你没有多租户的问题，环境变量在 Linux
进程间的可见性对你没有意义——能读到它的人本来就能做更多事。把精力花在加好
.gitignore、检查备份里有没有明文 API key 上。

你是不是需要在多台机器上管理同一批密钥，或者需要经常轮换它们？
如果是，集中式管理（1Password、Infisical）带来的操作便利是实质性的安全增益。重要的不是那个
vault，是轮换只做一次。

你的服务是不是通过互联网可以被直接访问？
如果是，最优先的一步是把密钥从环境变量里移走，改用 systemd credentials
或 Keychain 做运行时注入。这件事比选什么 secrets manager 重要得多。

一条原则可以覆盖剩下的选择空间：如果 AI
助手能读到某个文件的内容，这个内容就应该被当作已经在日志里了。从这个角度倒推，.env
里的 TAVILY_API_KEY
没你想象的那么可怕——它是一个独立凭证，泄露后轮换就行。但一个能解锁所有密钥的
SA token 出现在 agent
可读的文件里，就是另一件事了。收窄它的作用域，缩短它的生命周期，把它自己放进
Keychain。或者，如果你知道你的 AI 助手会读什么文件，就别把 master
credential 放在它看得到的地方。