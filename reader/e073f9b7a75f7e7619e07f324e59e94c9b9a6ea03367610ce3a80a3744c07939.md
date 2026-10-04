---
author: AI Engineer
date: '2026-04-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EmhRyw6xeT0
speaker: AI Engineer
tags:
  - model-context-protocol
  - identity-access-management
  - enterprise-security
  - cross-app-access
  - id-jag
title: 一键登录：MCP 跨应用访问（XAA）的技术演进与企业级实践
summary: 本文由 WorkOS 的 Garrett Galow 主讲，深入探讨了模型上下文协议（MCP）在企业环境下面临的身份验证挑战。核心介绍了跨应用访问（XAA）技术及 ID JAG 规范，旨在消除冗余的“授权弹窗地狱”，同时通过身份提供商（IDP）强化 IT 团队对 AI 代理访问权限的集中管控与实时安全撤销能力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Garrett Galow
companies_orgs:
  - WorkOS
  - OpenAI
  - Anthropic
  - Okta
  - Microsoft
products_models:
  - MCP
  - Cursor
  - Claude
  - Figma
  - Microsoft Entra
media_books: []
status: evergreen
---
### MCP 的应用困境：被“授权弹窗”淹没的开发者体验

在当前的 AI 开发生态中，**模型上下文协议**（Model Context Protocol: 一种允许 AI 模型安全访问外部工具和数据的开放标准）正被广泛采用。然而，随着开发者在 **Cursor** 或 **Claude** 等客户端中集成的 MCP 服务器增多，一个显著的用户体验瓶颈随之出现：**授权弹窗疲劳**（Consent Screen Fatigue）。用户每连接一个新工具（如 Figma 或 Notion），都必须经过繁琐的 OAuth 流程，点击确认那些往往并不会被阅读的声明。

对于个人开发者而言，这或许只是几秒钟的干扰，但在**企业规模**（Enterprise Scale）下，这种碎片化的操作流程演变成了显著的生产力损耗。更严峻的问题在于 **IT 团队的管控缺失**：MCP 服务器的连接往往绕过了企业传统的 **身份提供商**（Identity Provider: 简称 IDP，如 Okta 或微软 Entra），导致 IT 管理员无法感知员工连接了哪些外部服务，也无法有效拦截未被授权的 AI 代理访问敏感数据。此外，由于传统的 OAuth 令牌生命周期较长且缺乏集中撤销机制，一旦发生安全事件（如近期发生的 npm Axios 依赖包受损），IT 团队很难快速阻断本地机器上已建立的 MCP 连接。

<details><summary>Original English Source</summary>
If you've used MCP at all extensively, you know that it means consent screens on top of consent screens on top of consent screens. Who here uses MCP servers on the regular? Okay, most of you. if you want to use MCP servers with cursor, you add them in. You have the little config file. And then in each one of these, if you want to use it, you have to connect. It'll pop up this window. You have this nice little consent screen that you're not going to read. You're just going to say okay... and you need to do this for every single tool, which is frankly pretty annoying.

And uh that's not fun, but it's in a company with a lot of developers. It's not just one person's inconvenience. Uh as a user, you might log into a half dozen or a dozen MCP servers. Um but when you combine that together across your team, you basically have dozens and dozens of people spending all this time managing all these consent screens... The real problem comes in um for the IT team like the people managing all these applications. Uh MCP doesn't work the way that they want it to work. You know, it can't really tell like what MCP servers you may or may not be using... They basically can't determine uh you know which AI agents you can actually use, right?

I don't know how many people heard about the npm Axios package getting popped about a week ago. Uh unfortunately I was uh hit by that... our IT team, you know, became aware of that problem. They were able to detect that you know my machine had been compromised. They were able to cut off network access to my machine. they could invalidate my octa sessions across all the applications... but you know in my local machine I had MCP servers connected I had like API keys that I was using... how do we go revoke that? how do we ensure that you know my system safe?
</details>

### 跨应用访问（XAA）：基于信任桥接的身份管理方案

针对上述挑战，WorkOS 提出了**跨应用访问**（Cross-App Access: 简称 XAA）解决方案。其核心逻辑是将身份提供商（IDP）转化为应用程序之间的**信任中介**。在企业环境中，用户通常已经通过 **单点登录**（Single Sign-On: 允许用户一次登录即可访问多个相关应用）登录了 Cursor 和 Figma 等工具。

**XAA** 的精髓在于利用现有的信任链：既然 Cursor 和 Figma 都信任同一个 Okta 实例，那么 Cursor 就可以通过 IDP 获取访问 Figma 的凭证，而无需用户进行手动干预。这种模式将身份验证的控制权从碎片化的本地应用收回到集中的 IDP 手中，实现了“一键登录，通行全域”。在建立这种集中式的心理防线后，具体的底层技术实现则依赖于一种新兴的行业规范。

<details><summary>Original English Source</summary>
The solution is cross app access otherwise known as XAA. XA is basically a way in which the identity provider can act as a standin a trust provider between applications. so let's say the example of I have cursor that's my MCP client uh Figma is the MCP server I want to connect to and then octa is the IDP that we use at our company for logging into things. so both cursor and figma already have this trust relationship ship with octa right? what cross app access does it helps bridge the gap between cursor and figma but providing a way for cursor to talk to Figma they can both depend on that trust reliance on octa and they can get credentials issued without manual or human intervention.
</details>

### ID JAG 技术架构分析：隐形授权的底层逻辑

XAA 的实现基于一个被称为 **ID JAG**（Identity JWT Authorization Grant）的规范。它允许 IDP 签发一个特殊的 **JSON Web Token**（JWT: 一种紧凑的、URL 安全的、用于在各方之间传输信息的身份验证标准），该令牌可以在不同的服务之间安全地传递身份信息。

在实际的流式操作中，整个过程对用户是完全透明的，共分为四个核心步骤：
1.  **初始 SSO 登录**：用户通过 IDP 进行常规的单点登录，客户端（如 Claude 或 Cursor）获得 **ID 令牌**（ID Token）和 **刷新令牌**（Refresh Token）。
2.  **获取 ID JAG 令牌**：客户端向 IDP 申请一个针对特定目标（如 Figma）的 ID JAG 令牌。IDP 会校验策略，确认客户端是否有权代表用户访问该目标。
3.  **令牌交换**：客户端将 ID JAG 令牌发送至 MCP 服务器（或其授权服务器）。服务器验证其有效性后，返回标准的 **访问令牌**（Access Token）。
4.  **业务通信**：客户端使用获取的访问令牌与 MCP 服务器进行常规通信。

这种架构的显著优势在于其**动态性**和**安全性**。由于访问令牌通常仅有 5 分钟左右的有效期，只要用户的 SSO 会话被 IDP 终止（例如员工离职或机器被入侵），系统在下次令牌自动续期时就会失效，从而实现了实时的权限阻断。

<details><summary>Original English Source</summary>
ID JAG is uh happens to be the name of the spec that that all this technology is built off of. Stands for identity JWT authorization grant. Effectively, it just means a token issued by an IDP that can be used across services to uh manage access.
The whole point of this is you don't have to do anything, right? So, it doesn't it appears as like it's sort of automatic... the client goes back to the IDP says, "Hey, I have this refresh token for Garrett. Would you please give me this ID Jag token that will work with Figma?" Uh, Octo basically knows about Claude, knows about Figma. It can check, hey, is Garrett a member of both of these applications? .. Octa will send back this ID Jag token to cla code. Then Claude sends that to Figma... verified and correct, it is then able to issue this access token back to cloud code.
Steps two and three here are totally invisible to the user, right? Once you've logged into the IDP... Steps two and three are done behind the scenes.
The other thing around this is... that access token that's being issued, uh, that could be very short-lived. So most applications issue access tokens around five minutes. ... once that access token expires I won't beble to get back in I won't be able to connect to that MCP server.
</details>

### 生态系统构建：从管理员到开发者的协同实现

要让跨应用访问成为现实，需要生态系统中三个关键角色的配合：

*   **IT 管理员**：在 IDP（如 Okta）的管理后台中配置“管理连接”。管理员可以明确授权，例如：“允许 Cursor 请求访问 Figma 的权限”。这种声明式的政策极大地简化了入职流程，新员工只需一次登录，所有预设的 MCP 连接即可自动就绪。
*   **MCP 客户端（如 Cursor/Claude）**：需要集成兼容 XAA 的 SSO 连接。目前 **WorkOS** 已经为这些领先的 AI 工具提供了底层支持，简化了 ID JAG 令牌的申请与交换逻辑。
*   **MCP 服务器开发者**：服务器端需要宣布支持 `JWT Bearer` 令牌类型，并能够与 IDP 通信以验证接收到的 ID JAG 令牌，最后签发业务层面的访问令牌。

虽然目前 **Microsoft Entra** 尚未原生支持 XAA（正在推进中），但该规范正逐渐成为行业标准。Garrett 提到，虽然这解决了身份验证（Authentication）的“你是谁”问题，但关于细粒度授权（Authorization）的“你能做什么”仍是未来扩展的方向，目前的实践依然遵循用户在目标系统中原有的权限配置。

<details><summary>Original English Source</summary>
On the setup side... Inside of a system like octa, there's this new kind of manage connections portal where you basically come in and say, hey, which app do I want to grant the ability to request access to this other app? So in this case, we're saying cursor can request access to Figma.
On the MCP client... One, you need to have an SSO connection that's XA compatible. ... your client requests IDJ token from the identity provider. You get that token back. You need to make that exchange request to the MCP server.
On the MCP server side... The first is there's this new um JWT bearer type that you need to support. ... you need to verify them. So there's a step where you go to the identity provider the octa URL and say like hey is this a valid token. ... then last uh which should be kind of the normal thing is issue the access token.

Question: this solves authentication not authorization. Does this do anything to to help with that?
Answer: By default no. Uh so this is p kind of just around the authentication bit. Um this is still you know you're logging into Figma uh as yourself you know so you're getting the permissions that you have uh with Figma. One of the things we're kind of talking about is like okay how do you extend this to be able to um define like scoped access. That's not something that's like part of the spec today.
</details>

### 前沿议题：多平台支持与协议标准化

在演讲的最后，Garrett 与现场观众讨论了一些深层技术细节。目前的 XAA 支持主要集中在基于 **OIDC**（OpenID Connect: 基于 OAuth 2.0 协议的身份层）的连接上，未来将扩展到 **SAML**（Security Assertion Markup Language: 一种基于 XML 的开放标准数据格式，用于在身份提供者和服务提供者之间交换身份验证和授权数据）。

关于 **Microsoft Entra** 的兼容性，Garrett 指出目前存在一些协议碎片化问题，如资源参数匹配和 **DCR**（Dynamic Client Registration: 允许客户端在运行时动态注册到授权服务器）的支持差异。业界正在从 DCR 转向 **CIMD**（Client Identification and Metadata: 一种更先进的客户端标识与元数据定义标准），虽然 CIMD 目前的生态采纳率尚处于起步阶段，但它预示着一个更标准化、更无缝的 AI 代理互操作未来。

<details><summary>Original English Source</summary>
Microsoft doesn't hasn't yet added XAA support inside of intra. Um, that's something we're working with them on. .. today with Octa, this is supported for OIDC based connections. Um but they're they're going to support this for sample based connections as well.

Question: Intro doesn't support DCR so that creates issues.
Answer: Yeah that's um kind of I think a general problem in the wild... CIMD is like the new standard that kind of supersedes uh DCR. ... It's like a metadata document that defines clients up front. So, you don't have to create the clients every time. Um, but that one has even less broad support in the ecosystem because it's, you know, it's like three months old. Um, but it is like a better experience. So yeah, there's still a little bit of um catchup in the ecosystem to you know uh supporting like the latest spec.
</details>