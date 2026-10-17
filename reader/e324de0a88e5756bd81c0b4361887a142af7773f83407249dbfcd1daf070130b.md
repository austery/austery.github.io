---
author: AI Engineer
date: '2026-07-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=lMCxVorb9wM
speaker: AI Engineer
tags:
  - agentic-security
  - identity-access-management
  - model-context-protocol
  - fine-grained-authorization
title: 重构 AI 时代的安全底座：为什么以人类为中心的安全架构已无法适配智能体？
summary: 随着 AI 智能体（Agents）从确定性编程走向概率性决策，传统的基于人类用户或静态服务账号的身份与访问管理（IAM）机制正面临巨大挑战。本文探讨了智能体带来的非确定性风险，分析了当前 OAuth 机制在细粒度权限控制上的局限性，并提出了面向智能体的微观授权与可观测性安全实践。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Scalekit
  - Freshworks
products_models: []
media_books: []
status: evergreen
---
### 重构 AI 时代的安全底座：为什么以人类为中心的安全架构已无法适配智能体？

### 频次危机与假设的破灭

在身份与访问控制的演进历程中，许多看似合理的系统假设往往被突然的技术范式转移所打破。**Scalekit** 团队在对其**身份与访问管理**（Identity and Access Management: 管理用户身份及系统访问权限的安全框架）基础设施进行性能监控时，发现系统每隔 15 分钟就会出现规律性的延迟峰值。深入分析后发现，系统在数据库写入层面承受了非预期的压力。其底层设计源于传统的“人本设计”惯性：系统为每位用户设计了“最后在线时间”的时间戳，以便预测用户活跃度。在**人类用户**为主导的时代，这种设计运行良好，但在过去一年多时间里，当**智能体**（Agents: 能够自主规划并使用工具执行任务的 AI 系统）开始大量接入 API 后，数据更新频次瞬间暴增了 60 倍。由于智能体以机器速度进行高频交互，直接导致高频的数据库写入请求，造成了系统级的延迟抖动。为了缓解这一数据库压力，团队不得不将更新机制从实时写入优化为按秒级进行批量处理。这一现象揭示了一个深层架构问题：**为人类活动设计的状态同步机制，在面对高频并发的智能体访问时正面临全面失效。**

<details>
<summary>Original English</summary>

Hi, thank you so much for tuning in. I'm Ravi, I'm one of the co-founders of Scale Grid. Today, I'm going to talk about how you need to think architecturally from the ground up about building your applications APIs, your MCP servers for agents, and how the human-focused architecture doesn't scale well for agents.

So, a while back, we were looking at our performance and latency numbers, and one thing that kind of jumped out at us was how our latency was spiking every 15 minutes in a rhythmic manner. Nothing harmful, but just a curious thing for us to analyze. What we noticed was very interesting. So, in our identity and authentication infrastructure platform, we have this little timestamp that we mark for every user to say, "Hey, when was the user last seen?" or "When was the user last active or last acted in our system?" so that we can predictively say, "Hey, this user is an active user. This user is not so active." But, one thing that we realized was this system was predominantly built for humans, but when agents started hitting our APIs in the last 12 months or so, we realized that this last seen update is happening 60 times faster than what it would, and that is creating unnecessary pressure in our DB write system. So, of course, it's a harmless thing. We were able to fix it very easily. We would just batch the update at a second level and not at every single time we had to update it.

That kind of took us down a rabbit hole. So, the assumption that broke was how often would our system have to update this timestamp on every row, and that's okay. It's just about speed, it's about latency, etc. But, what I was worried about is, "Hey, what if some of our assumptions that we made about authentication, authorization need to be rewired and rethought completely when it comes to agents because we would have designed earlier for humans as actors in mind?"

</details>

### 确定性安全模型的终结

回顾过去十余年身份平台的构建历史，传统的安全信任模型建立在两个核心支柱之上：第一是**人类用户**通过 Web 或移动端进行交互，并使用 API 密钥进行程序授权，此时“身份验证主体”与“实际操作主体”具有强一致性；第二是传统的**服务账号**（Service Account: 供非人类主体如应用程序访问系统资源的虚拟身份），主要依托 SPIFFE 或 OAuth 协议赋予机器独立凭证。在这两种场景下，系统均遵循一个基本原则：在注册时定义好固定的权限范围，后续所有操作都在该范围内严格执行。这一机制能稳定运行几十年的底层逻辑在于**确定性编程**（Deterministic Programming: 逻辑路径完全由人类开发者预先设定、行为完全可预测的编程范式）。开发者编写的代码是确定性的，系统拥有绝对的保障去确信程序绝不会越界。然而，**AI 智能体**彻底打破了这一“确定性”假设。智能体的决策过程是概率性（Probabilistic）而非确定性的。即便在相同的输入下，也无法 100% 保证智能体在下一次运行时会采取完全一致的行为。这种非确定性特征，使得传统的基于静态注册期权限的安全防线瞬间崩塌。

<details>
<summary>Original English</summary>

Now, just to give you a context, I worked on identity and authentication operations for the last 10 years building an identity platform at Freshworks, which is being used by millions of daily users, hundreds and thousands of customers all over the world. But, this is predominantly human users, right? Or at best, APIs. But, the way I think about it is APIs are also accessed by machines that are written by humans. That's not too bad, right? But, what I realized is the fundamental picture has changed drastically in the last three, four years or so. We have a unique ringside view to see how developers nowadays are building agents and how they're giving context to these agents with data from third-party applications like Salesforce or or Databricks or HubSpot or Notion. What we have realized is most of the agents our customers are building have way too permissions and scopes than the agent's responsibility or the agent's job is. Again, it's not because the developers who are building the agents are careless, but somehow this became a default pattern of giving the agents what they need access to, and the existing primitives that we have don't let us give extremely fine-grained permissions to the agents.

Now, I'll tell you how we ended up here, right? We predominantly have two slots, and neither of the slots was built for agents in mind. There's a human who's acting the application, either a web application or a mobile application, or their own little script that they wrote, and they give it their API key so that their program can access data from the application. This is all the fundamental principle here is it's the same user who is authenticating, and it's the same user who's acting, right? And the second slot is the traditional service account scenario or end-to-end account scenario where you create a service account, you give it certain permissions, and then say this machine has its own identity. That's where the likes of SPIFFE and and OAuth and all of that came into picture, but you would give them certain credentials and say, "Hey, now this machine has access to whatever data that it needs at any single point of time." And this is the existing pattern, right? So, the fundamental philosophy that we've always maintained is whoever is authenticating is the one that is acting. Every action the program or the human takes is based on fixed set of permissions that actor was granted at some time. If you take traditional authentication mechanisms for humans, including password, you just say, "Hey, if an identity has the same password that it was set at the time of registration, if they come back and if they present the same password again, then you say, "Okay, this is how I validate the identity. This is how I authenticate the human." And every action subsequently is tied to that human identity. Again, the same is the case with API key or the same is the case with web session tokens or even the same case for service account. You define the permissions at the time of registration, and then every single time it acts based on the registration time permissions and scopes.

Now, this is okay all this while because for decades the service account and OAuth principle even is working fine even though there are their own problems, but it's still working fine because these machines are using a program in a deterministic way by the way the human developer wrote that program. So, there is absolute guarantees about what the program could or what the program won't do, but it is still intentional based on what the human wrote, right? In this particular case, again, if it is using API keys, then that actor and the principal is the same, then there is some sort of a delegated permission for the program to act based on what consent the user has granted. But, the second one is the most important part, which is it's a deterministic program, and it always stays in its own lane. It can never do what it was not programmed to do. And you could inspect the code to say, "Okay, is the program doing what it's supposed to do?" Even if you apply for a Google developer account, and then ask for client ID, and you need to access these scopes, you have to go through a security review. So, what they're doing is they're looking at your code base to see, "Are you doing enough checks? The appropriate practices in place?" So, these programs are deterministic. These programs behave the exact same way a developer programmed them to work. But, agents fundamentally break this assumption. Right?

</details>

### 被动暴露与过度授权的风险

在智能体应用场景下，“委派授权”的脆弱性暴露无遗。首先，智能体的“验证主体（Principal）”与“执行代理（Actor）”高度分离。例如，智能体需要代表用户访问其 Gmail 或 Salesforce 等系统，但目前的底层技术体系中，有大量的系统甚至无法原生支持 **OAuth 协议**（Open Authorization: 允许用户授权第三方应用访问其受保护资源的开放标准）。这导致系统在运行时根本无法区分到底是用户本人在进行操作，还是一个代表用户的智能体在代为执行。其次，在更广泛的 **模型上下文协议**（Model Context Protocol: 连接 AI 智能体与外部数据源和工具的开放协议）服务端设计中，安全隔离机制极度匮乏。现有的 MCP 服务通常会直接把该用户拥有访问权限的**所有工具与数据接口**全部暴露给智能体，而非基于当前的特定任务上下文做动态裁剪。这无异于将全量系统控制权移交给了具有概率性行为特征的智能体，当智能体因为意图解析错误而调用了错误的工具（例如误将生产数据库清空），灾难便无法避免。**过度授权与缺乏上下文约束的工具暴露，是当前智能体安全架构中最致命的漏洞。**

<details>
<summary>Original English</summary>

First of all, in the case of agents, the principal is not the same as an actor. You need to give delegated access, so that the agent can act on behalf of the user. Agent can access the user's Gmail. Agent can access the user's Salesforce data, and whatever the case may be. But, again, unfortunately, not a lot of systems, even today, support OAuth. So, here again, there is no on behalf of principal that is working. So, you don't even know if there is a program that is acting on behalf of the user, or the user acting by themselves. Right? That's a fundamental problem.

The second problem is even more dangerous, which is right now, the program is not written by human. There is no determinism baked in to say what the agent will do or won't do. Right? Just because an agent does certain things today, you can't be 100% certain that the agent can't do the same or the exact same thing tomorrow, day after, or even if it's the next immediate run. Right? Because of this non-deterministic nature of agent, we usually pick one of the two lanes, right? You give a specific identity to the agent, which is what we call as client ID in the context of OAuth, and then say, you act on behalf of this particular user, or we go back to the agent acts as the user, which is even worse.

The fundamental reason why I'm harping on the same thing is because when an agent is acting on behalf of user one versus user two or user three, the agent needs specific permissions based on the user's context. Now, the OAuth solved this perfectly fine by saying, hey, the user will grant specific scopes or permissions to the agent. So, when the agent is acting on behalf of the user, it can't do everything, but the agent will only do certain things. Now, in the kind of the world that we're living in, most of the MCP servers that we've worked with don't actually limit the tool context access to the agent based on which user authorized the agent. They typically surface all the tools that the user has access to, or all the tools that the application can even support, and then let the agent determine what they are can or cannot do. And now the agent ends up picking the wrong tool, doing wrong things. Maybe there is some runtime check in the application that prevents some of these things, but the agent is still seeing the same surface regardless whom it is acting for.

</details>

### 构建智能体专属的安全防御机制

为了应对智能体带来的安全范式转变，开发者必须从底座重构安全防御系统。核心解法是从“人类视角”过渡到“智能体视角”，构建**细粒度授权**（Fine-grained Authorization: 基于高维度属性及上下文对访问请求进行精准判定和限制的机制）和基于时间与维度的限制。传统的 OAuth 范围（如 Gmail 的 `send_mail`）在智能体时代过于宽泛，需要下钻到具体的属性和上下文级别（Attribute-Level / Context-Level Scoping）：
* **时间段限制**：限制智能体仅能在特定的工作时间段执行写操作；
* **发送方/接收方约束**：限制智能体只能读取指定发件人的邮件，或只能向特定白名单内的收件人发送邮件；
* **动态工具裁剪**：根据智能体当前执行的特定任务目标，动态展示最小化的工具集，防止其接触无关敏感接口。

此外，必须遵循“**最小特权原则**”（Least Privilege: 仅授予主体执行当前特定任务所需的最小权限）以及“**即时提升授权**”（Just-in-Time Authorization: 临时性、按需提升操作权限的动态授权模式）。如果智能体需要更高权限的范围，必须触发显式的人类确认或审批流。最后，架构必须具备**全链路可观测性**（Full-chain Observability）：每一条指令由哪个智能体执行、代表了哪位用户身份、谁在何时授予了该授权、授权有效期是多久，均须保留强不可篡改的安全审计日志。在生产环境部署中，正如业界先驱 **ref.tools** 在为其代码智能体构建上下文环境时所实践的那样，唯有依赖这种确定性的安全边界，才能约束非确定性的智能体行为。

<details>
<summary>Original English</summary>

Now, two things that we need to solve for. One is the actor, in this case, an agent, has to be bound to the principal at all times. And the agent should have its own identity. Agent should have extremely fine-grained credentials, not the OAuth scopes that we are seeing today. If you inspect the scopes for some of these applications, like even very popular applications like Gmail, it'll say, can this client send emails on your behalf? There's no extremely fine-grained scoping to say can this agent act at this hour? Can this agent read emails only from these senders? Can this agent send emails to only this recipients? The reason why that is important is because again, we spoke about this earlier in the context of non-deterministic agent workflows, it's extremely important that the agent should have permissions for limited amount of time that they're operating in number one. Every agent has a goal, every agent has a job. So, you should be able to deterministically say that this agent should have access only to those tools or only to those jobs it has access to. So, gone are the days when the broad scoped auth scopes that we defined is okay because in that case developer was writing a deterministic application and you can review the code to make sure that he's not doing anything sinister. But in the case of agents is extremely non-deterministic, it is probabilistic. Agents are bound to do things whatever they can get a hold of. So, in the context of when you're giving access to the agents, you should be in a position to give extremely fine-grained scopes. It should be at an attribute level scoping, it should be context level scoping, it should be principal level scoping. So, all of that is extremely important.

Again, I think everyone agrees that agents should be least privileged by default and they should be able to ask for just-in-time authorization if they want elevated scopes. Now, the reason why we're talking about this is because it's not some futuristic thing. It is happening today. We have seen enough incidents where agents end up doing rogue things. They end up deleting production databases and stuff like that. So, how do you put deterministic guardrails in place is an important problem to be solved right now. Again, one of our customers, ref.tools, they don't even have humans as actors. Their predominant product is about how to give context to coding agents so that they can do their job effectively. So, they built the entire OAuth scoping. How do you do things the right way and things like that. So, the reason why I give this example is not to say that this is a warning shot, but this is a problem of today and not for tomorrow. Before I go, you have to have absolute visibility into what your agent can do, every action that's taken in your system, who took it, on behalf of whom, and who authorized it, when was the authorization given, what authorization was given, how long is it given for. If you don't have visibility into all these actions at every single time, and if you can't deterministically control what your agent can or cannot do, then you're just praying that agent doesn't end up doing what it's not supposed to do. And praying is not a strategy, as we all know.

One last thing to take away. If you architected so far with humans and APIs in mind, you need to start rethinking about how you need to give deterministic guardrails and deterministic authorization controls to the agent. And OAuth is a good place to start, but you need something beyond OAuth to make sure that the agents have extremely fine-grained access controls, and agents are always acting by themselves on behalf of certain users. Thank you so much for your time.

</details>