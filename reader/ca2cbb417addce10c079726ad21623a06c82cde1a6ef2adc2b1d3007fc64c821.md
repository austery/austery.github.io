---
author: AI Engineer
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YqJ4asgj1R8
speaker: AI Engineer
tags:
  - agent-identity
  - token-exchange
  - durable-execution
  - least-privilege
  - workflow-orchestration
title: 停止向 AI Agent 授予裸 API Key：Keycard 动态凭据交换与 Temporal 持久化执行实践
summary: Keycard 的 Kim Maida 与 Temporal 的 Mason Egger 在工作坊中展示了如何通过 OAuth 2.0 令牌交换标准为 AI Agent 引入端到端身份委托链与细粒度作用域凭据，并结合 Temporal 的工作流持久化执行与拦截器机制，解决 Agent 权限过大、审计缺失及故障中断重试开销等问题。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Kim Maida
  - Mason Egger
companies_orgs:
  - Keycard
  - Temporal
products_models:
  - Keycard
  - Temporal
  - LangChain
media_books: []
status: evergreen
---
### 演讲者介绍与工作坊概览

**>>**: [音乐]

我叫 Kim Maida。我在 Keycard 工作，Keycard 在运行时为 Agent 提供身份与访问管理。

天哪。
<details><summary>Original English</summary>
[music]

>> My name is Kim Maida. I work at Keycard and Keycard provides agent access identity and access at runtime for agents.

Oh my.
</details>

**>>**: 大家好。我叫 Mason Egger。我是 Temporal 的解决方案架构师，Temporal 为各类软件应用程序（包括 Agent）提供持久化执行能力。所以不仅是 Agent，基本上涵盖了整个技术栈。
<details><summary>Original English</summary>
>> Hi everyone. My name is Mason Egger. I'm a solutions architect at Temporal and Temporal provides durable execution to your software applications up into and including agents. So, not just agents, but pretty much the entire the entire stack. So.
</details>

**>>**: 参加本次工作坊所需的所有资料都在屏幕上显示的链接中。实际上大家不需要提前注册 Keycard，因为注册流程已经包含在课程体系内了。但如果大家想在工作坊结束后获取用于个人使用的账号以便自行体验 Keycard，可以访问底部提供的链接，并输入注册码来注册个人账户。

好的。

稍后我们还会回到这张幻灯片，不过我首先要聊一聊 Agent 的访问权限问题。
<details><summary>Original English</summary>
>> So, everything you're going to need for the workshop is at the link that's on the screen right now. You actually do not need to sign up for Keycard ahead of time because the sign up will be included like within the curriculum, but in order to get an account for your own personal use, if you want to play with Keycard on your own after the workshop, you can go to the link that is provided at the bottom and enter that registration code in order to sign up for a personal account.

Okay.

So, we'll come back to this slide, but I am going to start out by talking a little bit about agent access.
</details>

### 裸 API Key 的缺陷与令牌交换原理

**>>**: 如今我们经常做的一件事就是直接给 Agent 提供 API Key，以此授予它们对各种资源的访问权限，对吧？这种做法存在若干问题。其一，凭据既不归属于某个具体的用户身份，也不归属于 Agent 自身的身份。

其二，Agent 对该 API Key 包含的任何及所有权限都拥有不受限制的访问能力。

最后，我们不可能到处都简单地加入人工介入环节（human-in-the-loop），因为人同样会犯错，而且许多 Agent 都是自主运行的。

我们在 Keycard 解决这个问题的方法是利用名为令牌交换（token exchange）的开放标准。这项标准早在 2020 年就已推出，它是对 OAuth 2.0 的扩展。接下来我将向大家演示我们今天要做的工作。

为了向 Agent 以及 Agent 背后的用户赋予身份，我们首要的任务是明确用户是谁。因此，由授权服务器来验证身份并颁发令牌。像 Google、Okta、Auth0 等身份提供商都提供授权服务器功能。

如果我们希望在 Agent 的执行路径中建立身份链，首先需要用户完成登录。

登录之后，授权服务器会提示用户授权同意，将自身对资源的部分访问权限（以称为 scope 的权限子集的形式）委托给 Agent。这是最初步的访问范围收窄，对吧？我们仅仅是将用户全部权限中的一部分委托给了 Agent。

随后，授权服务器颁发一个标识该用户身份并包含其访问权限等级的令牌。

现在我们来看看 Agent 执行路径中实际发生的流程：此时我们拥有了一位身份已知且已通过认证的用户，该用户希望通过 LLM 与下游资源进行交互。

Agent 本质上是一个调用 LLM 的控制循环。在本次工作坊中，该 Agent 是一个报销台（Expense Desk）Agent，这就是我们将要操作的对象。

它会调用一个报销 MCP（Model Context Protocol）服务器，该服务器位于 Agent 与账本（Ledger）API 之间。

这为 Agent 提供了一组定义明确的工具，同时也提供了通往下游资源的连接通道。

MCP 客户端接收 Agent 提出的工具调用建议，并将其分发给对应的 MCP 服务器。

运行时是一个与 Agent 循环一同运行并执行调用的进程。在我们今天的场景中，Expense Desk 应用程序就是这个运行时。

我们将在该自定义 Expense Desk 应用中使用一个基于 LangChain 实现的 Agent。

如果我们沿着执行路径追踪一次提示词调用：用户将提示词提交给运行时，运行时调用模型并将提示词发送给 LLM。模型提出工具调用建议，MCP 客户端将该建议分发给 MCP 服务器，MCP 服务器执行工具并调用资源 API。

API 向 MCP 服务器返回响应。

MCP 客户端将响应传递给运行时，运行时再次调用模型，该循环不断重复，直至模型完成处理并将最终响应返回给用户。

大家还记得，我们有一位已通过认证的用户，持有标识其身份的令牌。该令牌就变成了我们所说的“主体令牌”（subject token），因为它标识了 Agent 即将代表其行动的主体。

为了支持令牌交换，我们需要一个能够执行代码的 OAuth 客户端。这可以是一个位于 MCP 客户端与第三方 MCP 服务器之间的网关，也可以是一个自定义 Agent 应用，或者是围绕现成代码编写 Agent 的 CLI 包装器。

在今天这个案例中，Expense Desk Agent 是一个自定义 Agent 应用，它实现了用于访问 Expense MCP 服务器的令牌交换功能。

该 MCP 服务器同样支持针对下一个下游资源（即账本 API）的令牌交换。账本 API 则连接着实际存储报销数据的数据库。

现在，提示词和主体令牌被发送到 Expense Desk Agent 应用。Agent 循环启动，模型提出一项工具调用建议。

Expense Desk Agent 向 Keycloak 的安全令牌服务（Security Token Service）发起认证。这是一个特殊的授权服务器。

Expense Desk Agent 可以使用其客户端凭据（client credentials）或工作负载身份（workload identity）进行认证。同时它还会发送用户的“主体令牌”，声明用户的身份及其授权级别。

此时，Expense Desk 的 OAuth 客户端创建一份令牌交换请求，申请访问 MCP 服务器以执行该工具调用的权限，且仅针对这一项具体的工具调用。

因此，现在我们基本上掌握了三项信息：

1. 正在申请访问权限的 Agent 的身份；
2. Agent 所代表行动的用户的身份；
3. 用户授予该 Agent 的访问权限级别。

接下来我们需要决定是否应当颁发所申请的令牌。我们可以通过策略（policy）来做出决策，策略的评估依据包括：向什么资源申请了什么访问权限、Agent 是谁，以及 Agent 在代表谁行动。

如果委托链和申请的访问权限完全符合策略要求，Keycard 就会颁发一个访问令牌，且该令牌只能在对应的 MCP 服务器上使用。

这个新颁发的令牌通常在几分钟内就会过期，并且绝不应当持久化存储。

该令牌被发送至 Expense Desk MCP 客户端，客户端使用该令牌作为 Bearer 凭据向 Expense MCP 服务器发起工具调用。

MCP 服务器验证该令牌，随后使用它来授权该工具调用。

这些工具需要访问账本 API 资源。因此在那个节点上，MCP 服务器随即发起第二跳（second hop）。在此处，它向 Keycard 发送自己的令牌交换请求。

该请求申请将从 Expense Desk 接收到的令牌交换为访问账本 API（即下游资源）的令牌。

Keycard 依据策略对该请求进行评估，随后铸造（mint）针对该资源的凭据，且作用域严格限定在该特定工具调用所需的访问范围内。

MCP 服务器收到该令牌后，使用它调用账本 API。

API 验证该令牌并授予相应的受请访问权限。

MCP 服务器绝不会存储该令牌，调用一结束便立即将其丢弃。

API 响应随后沿链路反向返回，Agent 循环继续重复，直至模型将最终答案返回给用户。

从高层设计来看，这就是大家今天将看到我们使用 Keycard 实现的完整架构。
<details><summary>Original English</summary>
So, one of the things that we do a lot of these days is give API keys to agents to give them access to resources, right? And there's several problems with doing things this way. One being credentials aren't attributed to a user identity or an agent identity.

The agent has unrestricted access to any and all permissions in that API key.

And finally, we can't just sort of stick human in the loop everywhere because humans make mistakes, too, and many agents also run autonomously.

So, the way we solve this Keycard is by using an open standard called token exchange. This This standard has actually been around since 2020 and it extends OAuth 2 and I am going to show you what we're going to be doing today.

So, in order to give identity to an agent and the user behind the agent, we need to know who the user is as first order of business. So, an authorization server verifies identities and issues tokens. Identity providers like Google, Okta, Auth0, etc. provide authorization servers.

And if we want to get an identity chain in the agent execution path, then we need the user to log in first.

After logging in, the authorization server prompts user for their consent to delegate some portion of their access to resources with a subset of their permissions called scopes. Now, this is kind of the first narrowing of access, right? We're only delegating some of the user's total access to the agent.

And the authorization server issues a token I that identifies the user and includes their level of access.

So, now if we go into what actually happens in the agent execution path, we have an authenticated user now with a known identity who wants to use an LLM to interact with resources.

Now, an agent is a control loop that calls an LLM and in this workshop, that agent is an expense desk agent. That's what we're going to be working with. It's going to call in an expense MCP server which sits between the agent and a ledger API.

This provides the agent with a defined set of tools and it also provides the connection to that downstream resource.

Now, an MCP client takes the agent's proposed tool calls and it dispatches them to its MCP server.

The runtime is a process that runs with the agent loop and executes calls. So, in our case today, the Expense Desk application is the runtime.

We're going to use a LangChain agent that's implemented in this custom Expense Desk app.

So, if we follow a prompt through this execution path, the user submits the prompt to the runtime, which calls the model and sends it to the LLM. The model proposes tool calls, which are then dispatched by the MCP client to its MCP server, which executes the tools, and then calls the resource API.

The API returns a response to the MCP server.

The MCP client delivers the response to the runtime, which calls the model, and this loop repeats until the model is satisfied and returns the response to the user.

Now, if you remember, we have an authenticated user with a token identifying who they are. And this token becomes what we call a subject token as identifies the subject on whose behalf the agent is going to act.

So, in order to support token exchange, we need an OAuth client that's capable of executing code. So, that might be a gateway between the MCP client and maybe a third-party MCP server, or a custom agent app, or a CLI wrapper around an off-the-shelf coding agent.

In this case today, the Expense Desk agent is a custom agent app that implements token exchange for access to the Expense MCP server.

This MCP server also supports token exchange for the next downstream resource, which is the ledger API. This connects to the database where the expenses are actually going to be stored.

Now, the prompt and the subject token are sent to the Expense Desk agent app. The agent loop runs, and the model proposes a tool call.

The Expense Desk agent authenticates with Keycloak's security token service. Now, this is a special authorization server.

And the Expense Desk agent can authenticate using its client credentials or a workload identity. It also sends the user's subject token that declares the user's identity and their level of authorization.

Now the expense desk OAuth client creates a token exchange request asking permission to access the MCP server for that tool call, but only that one specific tool call.

So now we basically have three pieces of information.

We have the identity of the agent that's requesting access.

We have the identity of the user on whose behalf the agent is acting.

And we have the level of access that the user granted to the agent.

So now we need to decide if the requested token should be issued or not. And we can do this with policy, which is evaluated against what access is requested from what resource, who the agent is, and who the agent is acting for.

Now if the delegation chain and the requested access all fall within the policy, then Keycard issues an access token that can be only only be used at the MCP server.

Now this issued token usually expires within minutes and you should never store it.

The token is sent to the expense desk MCP client, which makes a tool call to the expense MCP server using that token as a bearer credential.

The MCP server validates that token and then uses it to authorize a tool call.

The tools need access to the ledger API resource. So at that point the MCP server then initiates a second hop. This is where it sends its own token exchange request to Keycard.

And the request to exchange that token is received from the expense desk for a token to access the ledger API, which is the downstream resource.

Now Keycard evaluates request against policy and then mints the credential for the resource scoped only for the access that's needed for that specific tool call.

The MCP server receives this token and then it uses it to call the ledger API.

The API validates the token and then grants the appropriate requested access.

Now, the MCP server never stores the token and it discards it as soon as the call is done.

The API response then flows back up and the agentic loop repeats until the model returns the answer to the user.

So, at a high level, this is what you're going to see us implement today with Keycard.
</details>

### 实操演示：从无身份 API Key 到 Agent 独立凭据

**>>**: 我再切回这张幻灯片。

再次说明，接下来我和 Mason 将在屏幕上逐步演示所有操作。大家可以跟着操作，如果只想观看也可以。

本次工作坊将使用一个预先配置好的共享 Keycard 组织。因此大家如果实际参与，会和现场所有人处于同一个组织中，能够看到其他人执行的操作。

如果打开提供的链接，大家会看到这个界面。这就是运行在沙箱环境中的工作坊。

我们现在启动它。启动并完成各项准备大约需要一两分钟。

这里的基本前提是：我们先从一个不需要登录的 Expense Desk Agent 开始。它在任何时刻都不知道操作者是谁，使用该 Agent 的所有人都依赖同一个 API Key。

现场有一些同事在协助填充演示数据。如果大家也想跟着操作，后续需要在 Keycard 中获取管理员权限。在操作过程中进入该环节时，工作人员会观察用户列表中出现的成员，并为大家开通管理员权限。

当大家进入工作坊时，看到的就是这个界面。在这个应用状态下，系统完全不知道任何人的身份。所有人共享同一个 MCP 服务器，但各自运行独立的 Agent。大家都在使用 API Key，可能使用的是同一个，也可能各不相同，我们对此无从知晓。

查看这个 Expense Desk，这就是典型的报销流程：提交报销单，然后被审批通过或拒绝，最后打款结算——当然本次演示并不会真正打款，大家不会收到钱。

整个报销台的一切操作都是通过 Agent 进行的。

我们要做的第一件事是提交一笔报销。我告诉 Agent 我想为工作坊零食提交一笔 75 美元的报销。

它提交了报销单，状态显示为待处理（pending）。

如果我们查看底部的活动日志，可以看到这笔报销是通过 API Key 授予的权限创建的，对吧？这里没有任何用户身份信息，也不知道 Agent 的身份，Agent 此时本身也没有独立身份。

我刷新一下页面。

现在我来审批或拒绝别人的报销申请。看一下这一条：如果我点击“批准”（approve），它基本上就是向 Agent 发送一段提示词。

Agent 批准了那笔报销，目前显示“创建者”（created by）是对应的这个 API Key。

所以我并不知道是谁创建了那笔报销，对吧？所有人都在裸用 API Key。由我批准了它，但系统里同样没有任何关于审批者是谁的记录，因为系统能拿到的凭据只有 API Key。

所以接下来我们要做的，就是真正赋予 Agent 一个独立的身份，让它能够代表自身来执行操作。

首先，我们要加入那个共享的 Keycard 组织。

跟着操作的朋友如果点击说明中的链接，会看到通过 GitHub 登录的提示，可以直接使用 GitHub 账号登录并加入 Keycard。进入后，左上角应当显示“workshop AI NYC”，这表明进入了正确的组织。我把窗口移动一下以便更清晰地查看。

好的。

加入组织后，大家很可能会看到几个授权同意提示。这正是我此前介绍的内容：将自己权限的某个子集委托给 Agent 代为使用。

这就是 Keycard 控制台。我首先要介绍的是“应用程序”（Applications）。在这里，应用程序与资源都是注册项（registrations）。

一个对象可以同时既是应用程序又是资源。具体而言，应用程序是能够发起令牌请求的实体，它们申请令牌交换，从而进一步向下游流转以访问其他资源。

我们要做的第一步是为我们的 Agent 创建一个应用程序注册项。在这里，我将其命名为 `agent app`。

因为所有人都在同一个组织内，为了方便辨识自己创建的应用程序与资源，我们在命名时加上各自的 GitHub 账号后缀。

每个应用的标识符必须保持唯一，因此这里我们也采用类似的命名规则。

我们选择使用隐式同意（implicit consent）。

接下来需要获取重定向 URL（redirect URL）。这可以从沙箱镜像中直接获取。

进入终端执行命令，获取专属于当前沙箱实例的重定向 URL。我将其复制下来。

将该地址添加为重定向 URL。在用户登录事件发生后，系统就会重定向回该地址。点击“创建应用程序”。

现在我们完成了一项注册，声明我们的 Expense Desk Agent 可以申请令牌了。但是，我们的 Expense Desk Agent 同时也需要具备接收令牌的能力，因为当用户登录时，它需要接收来自用户的主体令牌。

为了实现这一点，我们还需要做另一项注册，声明该 Agent 应用程序还可以充当“资源”（Resource），即它是令牌的目标接收方。

该 Agent 将接收到的正是此身份认证令牌。

进入“资源”（Resources）页面添加新资源。第一项是 `agent app`，这一项我们命名为 `agent resource`，同样加上我的 GitHub 账号作为标识符。

我将凭据提供方（credential provider）设置为区域提供方（zone provider），这本质上意味着由 Keycloak 作为负责处理令牌交换并为该资源颁发令牌的实体。

接着在下方配置该资源由哪个应用程序提供——选择之前创建的 `agent app`。

这一关联关系明确告知了 Keycloak：该应用程序被允许交换发往该资源的登录令牌。如果我们不建立这项关联，令牌交换请求就会被直接拒绝。

点击保存。

现在我要为 Agent 应用程序添加它所依赖的各项组件。返回应用程序列表，找到对应的应用进入依赖项（Dependencies）配置。

首先添加的是 `agent resource`，因为我们的 Agent 应用程序需要请求令牌交换以访问下游资源。

我们还需要能够为 Expense MCP 服务器请求令牌交换。这是一个已经预先配置好的资源，所有人共享同一个实例，大家无需各自以自己名字重复创建。

此外，我们希望将该 Agent 所需的 API Key 托管在 Keycard 中，避免将密钥以明文保存在磁盘上。Keycard 提供了凭据保险库（vault）功能，我们已经在保险库中预先配置好了该 LLM API Key，因此选择 `LLM API`。

最后勾选 `user info` 端点，以便系统能够获取已登录用户的身份信息。

点击连接。

下一步是赋予该 Agent 应用自身的身份。如果它没有凭据向系统证明自身身份以便“登录”，就无法做到这一点。

点击添加凭据（Add Credential），选择客户端 ID 与密钥（Client ID and Secret）。

进入编辑器，打开 `agent` 目录下的 `.env` 文件，粘贴生成的 Client ID 与 Client Secret。

我们在沙箱本地环境中通过文件进行配置；如果在生产环境中，通常会使用工作负载身份（Workload Identity）等机制。此外 Keycard 也提供了 CLI 工具，能够动态注入密钥而无需落盘。

最后填入该 Agent 资源的标识符（`agent resource` 加上 GitHub 账号后缀）。等待界面提示更改已保存。

至此，我们已经完成了 Keycard 侧的配置，使其能够处理令牌交换及其请求。

接下来需要确保 Expense Desk 应用程序代码能够正确处理这一流程。

查看代码目录，在 `agent` 文件夹下有 `agent auth` 相关代码。当前文件对应的是没有经过认证的 MCP 访问版本。

在工作坊的每个练习环节，我们都提供了对应的代码检查点（checkpoint）。我们切换到当前所在的练习二（exercise two）的检查点代码。

在检查点目录下找到对应的文件：可以看到这里传入了来自 Keycard SDK 的 `keycard zone token auth`。

每当 Agent 想要通过 MCP 服务器发起工具调用时，它都会发起这一令牌请求。

对于每一次单独的工具调用，我们都会获取一个严格限定在该工具调用范围内的作用域令牌。

查看 Keycard 文件中的 `mint` 函数，它负责发起铸造交换令牌的请求。

如果没有主体令牌（即当前没有登录用户），Agent 会通过客户端凭据许可（client credentials grant）完成代表自身身份的认证。

它使用 Client ID 和 Client Secret 向 Keycloak 证明自身身份，这意味着它完全是在代表自身行动。

回到终端标签页，执行命令切换到检查点二的代码，并重启服务。

服务重启完成。回到 Expense Desk 界面，此时页面提示可以作为经过认证的 Expense Desk Agent 继续操作。

点击“作为 Agent 继续”，我们向它提问：“当前正在使用的是哪个账户？我的审批额度是多少？”

这里的审批额度是指作为用户被允许审批他人报销申请的金额上限。

Agent 回答当前登录身份为 Expense Desk Agent（带账号后缀），这正是我们在 Keycloak 中配置了 Client ID 与 Secret 的应用程序。该 Agent 自身的审批额度大约是 50 美元。

接下来我指示 Agent：“代表我提交一笔 75 美元的报销，用于购买工作坊周边礼品。”

Agent 提交了报销。报销备注中写着“代表 Kim 提交”，但实际活动详情显示该记录是由该特定 Agent 创建的。

“代表 Kim”仅仅是我在提示词中输入的一句话，系统并没有任何机制对此进行验证。由于我本人并未作为用户登录，该报销实际上是 Agent 以自身独立身份创建的。

进入 Keycloak 控制台查看活动日志，这里记录了针对该应用程序发生的所有活动审计日志。

我们筛选最近一小时内对 Expense MCP 资源的调用。

可以看到系统通过客户端凭据许可颁发了一项凭据，这表明调用主体是应用程序自身，访问的目标是 MCP 资源。

再查看系统预配置的 Expense MCP 执行主体（actor）。Expense MCP 服务器同样有多重注册，因为它既能接收来自 Agent 应用的令牌，又能将该令牌向下游交换以访问账本 API。

我们在日志中筛选其调用账本 API 的记录。

查看其中一条调用记录可以发现其委托链（delegation chain）：发起请求的应用是 Expense MCP 服务器，它代表的是先前的 Agent 应用程序，访问的下游资源是账本 API。

这就是 Agent 以自身身份行动时的完整委托链记录。
<details><summary>Original English</summary>
So, again, I'm going to basically demo or Mason and I are going to demo everything step-by-step on screen. Uh you are free to follow along or if you would prefer to just watch, you can also do that.

Uh the workshop is going to use a pre-provisioned shared Keycard organization. So, if you do participate, you are going to be in the same organization as everybody else in the room. So, you'll be able to see what everybody else is doing.

Okay, so if you go to the link that is that was provided, you're going to see this. This is the uh workshop running in essentially a sandbox.

So, we're going to go ahead and start this. This is going to take a few min a minute or two to to uh get everything all set up.

But, basically, kind of the premise here is we're going to start with an expense desk agent that does not require a login. It doesn't know who is acting at any point and everybody who uses the agent is using an API key.

So, I have some folks uh here who are going to be helping to populate the demo, essentially. Um if you want to follow along as well, you would are going to eventually need uh admin access in key cards. So, as we go through the workshop, when we hit that part, uh they'll be watching to see people show up uh in the user list, and they will be granting you admin access as that happens.

So, when you begin the workshop, this is what you're going to see. So, basically, this is the application where we don't know anybody's identity. Everybody is using the same MCP server, but they're all running their own agents. They are all using an API key. They might be using the same one, they might be using different ones. We, you know, don't really have a way of knowing that.

But, if we look at the expense desk, it's we kind of see your your classical uh expense. You file an expense, and then it either gets approved or rejected, um and then paid out, which is not actually going to happen, so you're not going to receive money. Um

But, basically, everything in this expense desk operates through the agent.

So, the first thing we are going to do is we're going to submit an expense.

So, I'm going to tell the agent I want to submit a $75 expense for snacks for the workshop.

It submits that expense, and then its status is pending.

Now, if we go down to the activity here, we can see that uh this expense was created using access granted by an API key. Right? So, we don't have any user identity, we don't know the agent's identity, the agent doesn't really have an identity yet on its own.

And what I'm going to do is I'm going to refresh this.

And I'm going to approve or deny somebody else's expense.

So, let's see this one.

If I hit approve, it's basically uh just going to send that as a prompt to the agent.

It went ahead and approved that expense, and now we have the created by was created by this API key.

So, I don't know who created that expense, right? Everybody's just using API keys. I approved it, but we also don't have any record of who approved it, either, because again, all we have is an API key.

So, the next thing that we want to do is actually give the agent an identity, so that it can act on its own behalf.

Uh so, the first thing we are going to do now is we are going to join that shared Keycard organization.

So, if you click the link, if you're following along, if you click the link in the instructions, you will be able to you will get a prompt to log in with GitHub, and you can sign up with GitHub to join Keycard. When you get in, you should say see this workshop AI NYC in the upper left corner, indicating that you're in the right uh organization, and let me move this around so we can see things better.

Okay.

So, if you're following along, when you join, you're likely to see a couple of consent prompts. These are what I kind of talked about earlier in the presentation, where you are delegating some subset of your access to the agent to use on your behalf.

So, this is the key card console. The first thing I want to talk about is applications. Now, applications and resources are registrations.

So, something can be both an application and a resource. And basically, what this means is applications are things that are going to be able to make requests for tokens. They're going to ask for token exchanges in order to then exchange on down the line to access other resources. So,

our The first thing we want to do is we want to create an application registration for our agent. So, what we are going to do here is I'm going to call this agent app.

And then in order because we're all in the same uh organization here, we want to name things so that we can find our own applications and resources that we created. So, I'm going to use the my GitHub handle.

Every app's identifier needs to be unique. So, we are going to do something similar here.

We're going to use implicit consent.

And then we need to grab our redirect URL.

Now, this is something that we can get out of our uh sandbox image.

So, if we go into this.

I don't know why that one won't come to the front.

Go to the terminal.

We are going to run this.

This gives you the redirect URL that is specific to your instance of the sandbox. So, I'm just going to copy that.

I'm going to Oops, don't need to add this as a redirect URL.

So, after there's a login event, this is where the user is going to be redirected back to.

And I'm going to say create application.

So, now we have a registration that says our expense desk agent can request tokens, right? So, but our expense desk agent can also receive tokens because it's going to receive the subject token from the user when the user logs in.

And in order to do that, we basically need to do another registration, and we need to say that this agent application can also act as a resource, which means it is a target recipient for tokens.

So, the authentication token is the token that this agent is going to be receiving.

So, if we go into resources, we can add another resource. We are going to call this one The first one was agent app, this one is agent resource.

I'm going to use my GitHub name.

Let's use a similar identifier. This is the agent resource.

I'm going to set the credential provider to zone provider, which essentially means that Keycloak is the entity that's going to be handling the token exchange and issuing uh tokens for this resource.

And then I'm going to come down here, and I'm going to say this resource is being provided by my application, the agent app came out of.

So, basically, this is the relationship that tells Keycloak that uh this application can exchange sign-in tokens addressed to this resource. If we don't make this association, then the exchange requests are going to be rejected.

So, I'm going to save that.

And now I want to add the things that my agent application depends on. So, if I come back to applications, I find my application.

I'm going to go into dependencies, and then I'm going to look at the list of dependencies, and I'm going to add something here.

So, the first one I'm going to add is the agent resource, and we need this because our agent application is going to request token exchanges to access uh downstream resources.

We also want to be able to request token exchanges for the expense MCP server.

So, this is a resource that's already been preconfigured for you. Everybody is using the same one, so we don't need to create a bunch of them that are all named after ourselves.

Additionally, we have an agent, and we want to have the API key for that agent stored in Keycard so that we don't have its secret on disk. So, Keycard also provides a vault, and we have that API key configured in the vault already for you.

So, we can select the LLM API.

And finally, we're going to select this user info endpoint as well, because this is going to be able to tell us who the logged-in user is. It's going to be able to provide us with that identity information.

So, I'm going to say connect.

Now, the next thing I need to do is I need to give this agent app an its own identity, and I can't really do that unless it has some way to identify itself to essentially log in.

Uh so, I'm going to click on add credential. I'm going to click on client ID and secret.

Now, wait.

We're going to go into the editor.

We are going into the agent folder.

We're going to find the end file. And we are going to paste in that client ID and that client secret.

This is the secret.

Now, we're doing this because this is essentially like a sandbox local environment. If you were using this in a production environment, you would probably use work something like workload identity. Also, Keycard provides a CLI which can populate secrets for you dynamically and not require them to be on disk.

And then finally, I'm going to tell it what the identifier for the agent resource is. So, that was my your an agent resource and then my GitHub name.

Going to wait until this says changes saved.

And at this point, we have configured Keycard to be able to handle the token exchanges and exchange requests.

Now, what we need to do is make sure that our expense desk application can actually handle that.

So, essentially, when we go and look at the code here, we find that in the agent folder, we have this agent off.

If we go down, we find Okay, this thing is in the way.

I'm trying to move that.

This we're going to find the checkpoint, which So, this this is the file where we don't have any authenticated MCP access, right?

Now, the way the workshop works is if you at each lesson we have a checkpoint that will provide the code essentially for the end of that lesson. So, what we can do now is we can go and look for the checkpoint for exercise two, which is the one that we're at. So, if we go to checkpoints, we go to authenticated, and then we find the same file.

Where are we here?

Okay. So, we want to find this MCP tool set. This is passing in the keycard zone token off from the keycard SDK.

And this is what is going to actually make that token request every time the agent actually wants to make a tool call with the MCP server.

So, for every individual tool call, we're going to get a token that's scoped to that specific tool call.

Now, this call is the this is Okay. So, now if we go to the keycard file, we look for this mint function. This is what actually goes ahead and makes that request to mint a token for the exchange.

So, if we don't have a subject token, that is if we don't have a logged in user, then the agent is actually going to authenticate as itself using a client credentials grant.

So, it's going to use that uh client ID and client secret to identify itself to Keycloak.

And this means it's acting on its own behalf.

Okay, so now if we go to the terminal tab, we basically want to make sure that we activate this updated code.

So, we're going to uh run that so it switches over to checkpoint two.

And then we have to restart the services.

Stop. There it goes.

Okay, now if we go and look at the expense desk, we have the screen that will let us continue with an authenticated expense desk agent.

So, if we go ahead and click continue as the agent, then we're going to ask it uh which I can just copy this. Which account is being used right now?

And what is my approval limit?

And the approval limit is essentially the amount of money that you as a user are allowed to approve for other people's expenses.

So, it says I'm signed in as the expense desk agent K Mida, which was in Keycloak that was the uh specific application that we are acting as that we provided the client ID and secret for.

And the approval limit for the agent is about $50.

So next I am going to tell the agent file a $75 expense or let's just say for some swag for the workshop on my behalf.

So the agent submitted that expense. The memo says it was it filed on behalf of Kim but the actual activity details indicate that this was filed by this specific agent.

So the on behalf of Kim is just something I told it. It doesn't necessarily actually have any to verify that because I as a user have not signed in it created this expense under its own identity.

Okay. So now if we go into our applications actually I probably could have left that up. Oh, it's right there.

We can see the activity in Keycloak. This is essentially the audit log that Keycloak generates of all the activities that have been happening against this application.

And I am going to look for specifically because there's uh several different resources here. To look for the expense MCP resource. Anything that was calling the expense MCP resource, I'm going to limit this to the last hour.

And we can see that there was a credential issued using the client credentials grant, which means that the actor was the application itself, and it was accessing the MCP resource.

So now I'm going to go and look for what we have already registered for you, which is the expense MCP actor. So the expense MCP server has multiple registrations as well because it can receive tokens uh from the agent application, and then it can exchange that token on for a downstream token to access the ledger API.

So if we click on this one, now we have uh because everybody is using the same resource for the MCP server, we're going to go ahead and just filter it down to it calling the ledger API.

And I could technically use any of these, but oops, this is looking for people.

So if we look at one of the calls that the expense MCP server used executed in order to exchange the token that it received from the agent application to access the ledger API.

We can see that the delegation chain shows that the application that made the request was the expense MCP server and that it was acting on behalf of this application. And the resource that is accessing is the ledger API.

So, this is essentially the the record of the delegation chain for the agent acting as itself.

I'm going to go ahead and check that.
</details>

### 用户身份委托与双跳访问审计

**>>**: 好的。现在我们有了一个能够验证自身身份并代表自身行动的 Agent，但有时我们希望它代表我们行动，同时又不能冒充我们。我们不希望日志简单记录为“Kim 执行了此操作”，而是记录为“该 Agent 代表 Kim 并在 Kim 的权限范围内执行了此操作”。

因此下一步我们要将真实人类用户的身份引入此流程中。

现在进入用户委托环节。此时我们需要在新标签页中打开 Expense Desk，因为嵌入沙箱中的 iframe 无法处理外部认证重定向。

我们在外部窗口中打开它。右上角出现了一个“登录”（Sign In）按钮。点击该按钮。

由于我之前已经登录过了，它直接自动完成了登录。

现在可以看到我的邮箱显示在界面上了。

如果我现在问 Agent：“我现在使用的是哪个账户？”之前它回答的是作为 Agent 行动，而现在它识别出我拥有人类用户身份，因为我已经完成了人类用户认证。

与我的身份元数据关联的审批额度是 100 美元。

我还没有以人类用户身份提交过任何报销。如果将过滤器切换为显示所有报销，可以看到之前的报销仍然显示由 API Key 提交——引入新机制并不会追溯篡改历史数据。

我们还可以看到 Expense Desk Agent 代表其他人行动的记录。

现在我们既具备了作为人类用户代表自身行动的能力，同时也保留了 Agent 代表自身行动的能力。在本次工作坊中，这种分工体现为：Agent 拥有自主审批特定金额以下报销单的权限。

我提交一笔报销：比如为团队报销 30 美元的办公用品。系统验证我的身份，并提交报销单。

由于 Agent 自身具备独立审批 49.99 美元以下报销的权限，在报销单提交后，Agent 以自身身份对其进行了审批。

点击活动详情查看细节：记录显示这笔报销由我（我的邮箱地址）创建，随后由 Expense Desk Agent 批准。

日志清楚显示了执行审批操作的 Agent 标识符，并给出了批准原因：“符合条件的 50 美元以下办公用品，具有明确的业务用途”。

现在我们再试一次 75 美元的报销。如果提交的金额超出了 Agent 自主审批的额度上限，该报销单的状态就会保持为待处理（pending），需要人工介入审核。

如果我尝试让它通过：“我认为这笔报销应该被批准。批准报销单 123。”

Agent 提示：“我无法批准或拒绝由我自己提交的报销单，必须由其他审核人进行操作。”它之所以能做到这一点，是因为系统内现在拥有了身份上下文。我们不仅清楚所有登录用户的身份，也清楚 Agent 本身的身份。

在此之前我们没有演示过这种情况：当时由于系统不知道任何人是谁，我既可以批准自己的报销，也可以批准任何其他人的报销。

在列表中找到他人提交的一笔待处理报销，我选择拒绝它。

查看该报销单记录的活动信息：它是由 Expense Desk Agent 创建的（来自上一轮测试），而拒绝操作则明确归属于我的个人身份。

至此，谁提交了什么、谁批准或拒绝了什么，都有了清晰确凿的审计记录。

回到 Keycloak 控制台查看应用程序，筛选该 Agent 应用程序在最近一小时内的调用记录。

点击查看其中一项颁发的凭据：可以看到发起令牌交换请求的应用程序是我的 Agent 应用，它代表的是人类用户（我的邮箱），访问的目标是 Expense MCP 资源。

这就是第一跳（first hop）。接下来我们查看 Expense MCP 执行主体。

查看为访问账本 API 颁发的凭据：在第二跳中，发起请求的是 Expense MCP 服务器，它代表我本人发起请求，访问的目标是账本 API。

在第一跳中，Agent 获取了我登录时生成的登录令牌，向 Keycard 发起令牌交换请求，以该登录令牌换取链路下一环节（即 MCP 服务器）所需的令牌（主体令牌换取 MCP 令牌）。

随后它携带该 MCP 服务器令牌调用 MCP 服务器，执行带有相应工具级作用域的工具调用。

接着，MCP 服务器拿着从 Agent 处接收到的令牌，向 Keycard 发起另一次令牌交换请求，申请将其换取访问下游账本 API 的令牌。

我们可以跨跳追踪这一整个过程，因为它们都关联着同一个会话（session）。尽管我们不必花时间逐一比对会话编号，但通过在第一跳与第二跳中保持一致的会话 ID，任何特定的事件序列都可以被完整串联追踪。

我可以把这些窗口关掉了。接下来把麦克风交给 Mason。
<details><summary>Original English</summary>
Okay.

So, now we have an agent that can identify itself and act as itself, but we maybe want it to act on our behalf but without impersonating us. So, we don't want it to just say Kim did this. We want it to say this agent did this thing on behalf of Kim with Kim's permissions.

So, the next thing we're going to do is we're going to add human user identity into this process.

So, now we have user delegation. At this point, we need to load the expense desk in a new tab because the iframe that's embedded into the sandbox doesn't handle external authentication.

Um so, we're going to go ahead and open that in external window.

Put this down here.

And now we have this sign in button up on the right. I'm going to click that.

If it's spinning.

Okay. So, because I was already logged in, it went ahead and logged me in automatically.

Um but now what I can do is I can say we can see that my email is here.

If I ask the agent which account am I using now, before it said you're use you're acting as this agent, now it knows that I have an identity because I authenticated as a human user.

All right. And my approval limit, which is associated with my identity metadata, is $100.

So, I haven't filed any expenses under my human user yet. So, if I change this filter to to show all expenses, you can see that these expenses from earlier still um say that they were submitted by the API key. Like, adding all of this doesn't go back and change anything that's happened in the past.

And we can see, you know, examples of the Expense Desk agent acting on behalf of other people as well.

So, we have the ability now to act as ourself as a human user, but we have still retained the ability for the agent to act as itself as well. And the way that kind of plays out in this workshop is by the agent having the capability approve expenses that are under a certain amount of money.

So, if I I'm just going to do this one.

If I submit an expense for, say, $30 for office supplies for the team, it's going to verify who I am, it's going to file the expense.

>> And then because the agent actually has the ability to approve expenses under $49.99 on its own, it filed the expense and then the agent approved it as itself.

So if I click on the activity to examine what happened here, it says that this expense was created by me under my email.

And then it was approved by the expense desk agent.

So it shows, you know, that this is the identifier for the agent that acted in the approval and it gives a reason says eligible office supplies under $50 with a clear business purpose.

Uh so now maybe I want to Let's do this $75 one as well.

So if I submit an expense that is over that approval limit that the agent can act on on its own, then the status for that one is pending. A human needs to review it.

If I go and say, "Hey uh I think this should be approved. So I'm going to send the message to the agent that says, 'Hey, approve expense 123.'"

It says, "I can't approve or reject my own expense. So I have to ask another reviewer to do that." And it's able to do that because we have identities now. We know who all of the users are, who are logged in, and we also know the identity of the agent itself.

Uh so before we didn't demonstrate this, but before I could have approved [music] my own expenses or anybody else's because it didn't know who anybody was.

So if I go here, let's see.

Let's find somebody else's pending expense.

I'm going to say, uh, I want to reject this one.

The agent goes through that song and dance. And now if we look at the recorded activity for this expense, it says that it was created by the expense desk agent, uh, because it was from kind of the previous cycle.

And it was rejected by my identity.

So, now we have a kind of a clear record of who filed what, who approved or rejected what.

So, if we go into the KeyCloak console at this point, go to applications, we are going to find the Kitematic application.

I'm going to clear any previous filters. I think they're already gone.

I'm going to say actor, and I'm going to look for my email.

Change this to hour.

And if I click on one of these issued credentials, I can see that the application that, uh, made the token exchange request was my application agent app Kitematic, and it was acting on behalf of me, the human user Kitematic KeyCloak or Kitematic KeyCloak, and it was accessing the expense MCP resource.

So, that was the first hop, right? So, now if we go over to the applications again and we want to find the expense MCP actor.

Actually, I don't think we need to filter anything. It's all here.

And we go to a credential that was issued for access to the ledger API. We can now see that on the second hop, the expense MCP server made the request on behalf of me and it was accessing the ledger API.

So, on the first hop, what happened is the agent took my sign-in token that it acquired when I logged in as my human user and it exchanged the it made a token exchange request to keycard offering that sign-in token in exchange for a token for the next thing in in the uh chain, right? Which is the MCP server.

So, it exchanged the subject token for an MCP server token.

It then took that MCP server token and called the MCP server to make tool call with the appropriate tool scoped scopes.

And then the MCP server took that token that it had received from the agent and it made a token exchange request to keycard asking to give that token up for a token to access the ledger API, which was the next resource in the stream.

And you can trace these hops.

You can trace these things across hops because they have a session associated with them.

So, we're not going to spend a whole lot of time like digging into the the session numbers and copying them, but you can follow any specific sequence of events uh by the session number will be consistent on the first hop and also the second hop.

I can close all of that.

And I will now give it up to Mason.
</details>

### Temporal 持久化执行原理与 Agent 容灾

**>>**: 太棒了。非常感谢 Kim。这是我的缓步动物毛绒玩具 Ziggy，它一直跟着我到处走。我们展台准备了很多，大家离开前记得带一个走，无论是送给孩子还是留给自己都很合适。

刚才我们完整演示了如何在 Agent 中构建安全性与权限机制。但接下来的问题是：我们该如何部署这些 Agent，以确保它们能够完整执行直至结束而不发生崩溃？或者当它们确实崩溃时，我们知道该如何妥善处理，并可靠地将它们恢复运行，从而避免丢失执行进度、浪费大量时间与计算资源？

这就是 Temporal 发挥作用的地方。
<details><summary>Original English</summary>
>> Awesome. Thank you so much, Kim. I have my little plushy tardigrade Ziggy goes with me everywhere. We have plenty of them. So, make sure you grab one before you leave. Take one home for your kids or for yourself. No shame.

Whatever you'd like to do. So, we won't just walk through how to build all of this security and stuff into our agent and stuff. But now, how do we deploy these agents to ensure that they execute to their completion, that they don't fail or when they do fail, we know how to handle that, and we know how to reliably bring them back up so we don't lose all of our process and waste a whole bunch of time and compute. And that's where Temporal comes into play.
</details>

**>>**: [清嗓子]
<details><summary>Original English</summary>
>> [clears throat]
</details>

**>>**: Temporal 是一个持久化执行（durable execution）框架。它的核心工作机制是：接收你的代码，执行它，并维护应用程序的状态。如果应用程序发生故障或遇到错误，它会将状态重建或恢复至发生故障的那一点，并继续向下执行。对于函数调用等环节，如果分布式系统发生宕机，框架内置了自动重试以及各类故障处理模式。

在我合作的客户以及我们的用户群体中，我们频繁观察到的一个普遍需求就是：必须设法让 Agent 具备持久化能力。从本质上讲，Agent 本身就是一个循环，一个不断向外部服务发起工具调用的循环。

归根结底，Agent 就是在分布式系统之上增添了一点“思考能力”。我们在分布式系统领域已经解决的各种难题，同样适用于 Agent 循环，这也是 Temporal 的用武之地。它能保障应用程序持续稳定运行，避免数据丢失，避免重复调用 LLM、浪费 Token 等等，从而防止终端用户遭遇服务中断。

接下来我们简要介绍一下 Temporal 应用程序代码的组织结构。详细代码大家可以留待后续阅读，我不会展开深入剖析底层代码细节。但本质上，在 Temporal 系统中，你构建一个工作流（Workflow），并通过所谓的“活动”（Activity）来对其进行定义。最直观的理解方式就是父函数调用与子函数调用。我们将 Agent 循环实现为父函数调用，这就构成了工作流。而该工作流的每一次执行实例（例如 Keycard 每次为用户执行认证），就是一个 Workflow；其中的每一次工具调用，在本质上就是一个 Activity。这些 Activity 是我们预期可能会发生故障的环节；当故障发生时，我们既可以对其进行重试，也可以重建状态并观察后续处理结果。

这里是工作流调用的代码。苹果鼠标的滚动方向和我不习惯，由于用的不是我自己的笔记本，如果划错方向请见谅。

下方这里的 `async def` 代码块展示了一个 Activity 的具体形态。它看起来就是常规的 Python 代码。Temporal 是一个代码优先（code-first）的系统，你可以直接编写常规代码并挂接到任何所需的服务上。

这里是结算工作流（settlement workflow）代码：它允许我们配置重试频率，随后按顺序执行各项 Activity。我们有账本扣款（debit ledger）和标记结算（mark settled）两个步骤，能够向账本添加记录并将其标记为已结算。中间我们还设置了一个计时器，用来模拟人工审核所等待的时间。

大家可以看到这个 Activity 代码块，我想请大家关注顶部的第一个装饰器：`grant resource`。Temporal 在其代码库中暴露了许多原生原语，其中之一被称为拦截器（Interceptor）。它允许在代码执行的特定节点挂接钩子函数（hooks）。

这是 Keycard 团队实现的一项能力：每当该 Activity 即将执行时，拦截器会先向 Keycard 请求权限并获取身份凭据，返回后再继续执行。这样我们就能通过 Temporal 工作流和 Activity 完成认证，并维持 Kim 刚才介绍的身份隔离——每个独立的 Worker 都可以拥有自己的身份，也可以让整个 Worker 集群共享身份，同时保持对权限范围与访问级别的精确控制。

接下来我们要启动 Worker。我们已经预先配置好了 Temporal 应用和相关环境变量。

Temporal 采用 Worker-Server 执行架构：由 Temporal 服务维护执行进度、应用程序状态等核心元数据；外部则运行着一组 Worker 集群（可以理解为 Kubernetes Pod 或 Pod 内的进程），负责在请求到达时实际承接工作。

我们在终端中启动第一个 Worker，其进程 PID 为 572。现在我们有了一个自动运行的 Temporal Worker，它运行着上一节练习中构建的 Agent，能够自动接收报销请求。

随后我们触发结算流程。切换到客户端标签页，调用结算任务，可以看到生成了对应的 Workflow ID。

回到 Worker 标签页，可以看到 Temporal 应用正在输出其执行日志：正如大家所见，它成功扣减了 Token 并为本次调用铸造了凭据，目前正在运行中。在 Temporal Web UI 中刷新页面，可以直观看到正在运行的应用实例。

我需要迅速做个操作，然后再继续解释。按快捷键终止它——Mac 上的快捷键对我来说确实不太习惯。

应用程序刚才还在运行，执行到了账本扣款步骤，此时我强行终止了应用进程。大家可以看到，该应用程序的运行时状态完全消失了。在传统系统中，这可能会造成严重问题：我们要么必须提前将状态手动持久化到数据库，在重新上线时再重新反序列化加载。

但在 Temporal 中这完全不是问题，因为应用程序的状态就保存在这里。最早执行的 `debit ledger` 函数已经将其执行结果保存在了状态机中。这里记录了重试策略、活动任务完成状态以及扣减 4200 的结果。由于此时没有 Worker 在运行，系统开始报错告警：“没有任何工作节点在运行，工作流任务已超时。”应用程序处于停止状态。

现在我们回到 Worker 标签页。任何时候只要我们准备就绪，直接重启 Worker 即可。

应用程序瞬间恢复执行，仿佛故障从未发生过一样。它依据所有历史响应完整重建了 Agent 的整个状态，没有重复调用任何 LLM，也没有重新执行之前的任何 Activity 或函数。它拾取状态、回放动作并顺利推进，最终成功完成了整个执行过程。

为什么持久化对 Agent 至关重要？因为 Agent 本质上是循环。目前构建 Agent 所调用的很多环节都极其昂贵：大规模调用 LLM 成本高昂，有大量的 Token 开销，存在各种失败状态和复杂边界情况。假设一个长时间运行的循环在执行到第 12 步时突然丢失了全部应用状态，此时要么需要自己重新造一个类似 Temporal 的系统（在数据库中维护状态，并编写所有状态重建与重试逻辑），要么直接采用 Temporal 这类持久化执行系统，由它全权处理这些复杂问题。

这使得你的 Agent 即使离线、崩溃、LLM 服务商宕机、甚至 AWS 整个可用区发生故障都不受影响。一旦计算资源重新上线，Agent 就能在上次中断的精确位置原样继续执行。如果故障转移恢复得足够迅速，终端用户甚至完全感知不到服务曾经中断过。正如刚才演示的那样，用户原本就知道需要等待一分钟进行审核，期间 Worker 发生崩溃，而我们在 5 秒钟内将其重启，客户端用户根本不会察觉到刚才发生了故障。这就是 Temporal 的价值：它将底层的故障彻底屏蔽，保障执行流程持续向前推进。

值得注意的是：所有这些认证密钥从未保存在 Temporal 的事件历史记录中。

回到客户端执行脚本进行验证：这里有一个 Python 小脚本，它能检测并确认整个事件历史记录中没有传递过任何 JWT 令牌数据。在整个事件历史中，我们可以看到启动流程和执行结果，点击可以看到 `debit ledger` 的结果以及第二个函数 `mark settled` 的结算结果。但是在底层完整的事件历史记录中，你绝对找不到任何敏感密钥信息，因为我们根本没有对其进行持久化。

Temporal 基本上提供了两种防止敏感数据泄露的方式：其一是像 Keycard 为我们实现的那样使用拦截器——拦截器将数据和凭据与事件流完全隔离，只在即将执行调用的时刻动态注入凭据（类似于即时凭据机制，JIT credentials）。

Temporal 提供的另一项强大能力是载荷编码器（payload encoder）。在刚才的 Temporal Web UI 中，大家看到的数据是以明文显示的。用户完全有能力对其进行自主加密：Temporal 提供了完整的架构模式与库，用户可以启动一个 Sidecar 进程，定义加密算法与加密策略，这样所有流向 Temporal（无论是自托管还是云端版）的数据在底层都是加密的。Temporal 无法读取该数据，也不掌控用户的密钥。我们关注的重点是将这些流程按正确的顺序编排与执行。

以上就是关于 Temporal 以及如何使用它构建 Agent 的概括介绍。Temporal 拥有丰富的集成生态，支持 OpenAI、Pydantic AI、LangChain 等等。此外我们近期还在构建面向 Agent 的专用运行框架（agentic harness）。欢迎大家到展台深入交流。

总结而言：通过构建 Agent 身份体系与 Worker 架构，结合 Temporal 作为底层执行层，能够确保 Agent 在遭遇灾难性故障、API 宕机甚至云厂商可用区离线等极端情况下，依然能够正确、稳健地完成执行。我就分享到这里。
<details><summary>Original English</summary>
>> So, Temporal is a durable execution framework. So, essentially what it does is we take your code, we execute it, we maintain the state of the application. If the application were to fail, run into an error, things of that nature, it will reconstruct the state or rebuild the state to the point of failure and continue executing onwards. Certain things such as function calls and things if say a distributed system were to go down, there are built-in retries and all sorts of failure handling modes.

So, one of the things that we've seen a lot of with the customers that I work with and with our users is that we need a way of making your agents durable. And in reality, the agent loop is or the agent itself is just a loop. It's a it's a loop of ever calling tool calls to external services.

Agents are just distributed systems at the end of the day with a little bit of added spice on top with some thinking. But the problems that we've solved for distributed systems apply to agent loops, and this is where Temporal comes in. It works out really well to keep your application running and going so you don't lose data, so you don't have to re- call LLMs, uh tokens and all of that nature. So, you So, your users don't experience any sort of outage. All sorts of really awesome things with that. So,

what we're going to do a little bit is just kind of talk about a little bit of how you would structure uh Temporal application code. I'll leave this here for you to read later. I'm not going to dive super deep into the code itself, but essentially Temporal is a a system where you can you build a workflow and you define it by things what are called activities. Think parent function and child function calls. Easiest way to think about it. We implement our loop uh as a this parent function call and this becomes a workflow. And every single uh instance of or execution of this uh workflow, so like every single time we would have keycard go through and uh authenticate for user, that would be a workflow. And every single tool call is essentially an activity. These are things that can fail, that we expect to fail, and when they do fail, we either retry them or we rebuild the state and see what happens with it. So, we have our workflow calls here. I'm also I do the other direction for Mac Mac mouse. So, if I go the wrong direction, it's cuz I'm not not using my laptop. Um I remap everything on my computer. Uh and then down here you actually see like this async def SS. This is actually uh what an activity would look like. So, you it looks like normal Python code. It looks like the typical code you would write. Temporal is a code-first system, so you can build all of your things and hook it into anything that you would want. Um

so we have our settlement code workflow, which I'm not going to read through too much. I'll leave that to you for you. But again, it's a Temporal workflow that uh essentially allows us to set how often we want to retry, and then we execute the activities. We have our um our debit ledger right here and our mark settled. So, we're able to, you know, add something to the ledger and then mark it as settled. And we have this timer here in the middle for us to kind of simulate some like uh human-in-the-loop time that it would wait take for someone to do this.

Uh and then one of our activities uh for this, as you can see here, is uh this section right here, which is just the typical code. But I want to draw your line your eye to the to the first decorator on top, which is grant uh resource. So, Temporal exposes a lot of native uh primitives within its code base, uh one of which is what's called an interceptor. So, it allows you at certain points within the code to allow for essentially think of them as hooks. So, this is actually something that the Keycard team uh implemented, which is where whenever this um this activity is being executed, it actually goes and gets permission and gets an identity from Keycard, and then comes back, and essentially now we are able to authenticate this through uh our Temporal workflow and our activities through this, and we can maintain this identity separation that Kim was talking about, where you can have each individual worker have its own one. You can have a fleet of them have their own, but you'd be able to identify and limit scope, access, all of those wonderful things uh through there.

Um so, the next thing we're going to do is we're basically going to find uh our work I think we already did the workers' identity in Keycard. Yeah. Okay, so we're going to start our worker. So, we actually already set up our Temporal application and set up all of these uh environment variable configurations. So, let's go ahead and start uh our worker.

So, Temporal is a worker-server model a version of execution. You There's a Temporal service that maintains the execution, the application state, all of that. And then there's a fleet of workers. You can think Kubernetes pods, processes within a pod that your work as it's being uh as it gets as the request comes in.

So, from here we'll go to start worker, and we'll just start our first worker right here, and so, we have worker PID 572 running. So, now we have a uh automatic uh a Temporal worker that's running the agent that was just done in the previous thing in the previous exercise, which will automatically uh accept our uh expenses. So, we have our worker running right here, and we see our PID is 572.

And then we can start a settlement. So, what we're going to do is we're going to click on this client tab here, and we're going to invoke a settlement uh that's going to happen, and we'll see our workflow ID settlement came up.

So, if we go back to our worker tab here, we'll actually see the output of our Temporal application as it's logging out what it is doing, and it's currently doing it as you can see here, we debited a token um and minted it for this particular call, and then we're running it. If we go to our Temporal Web UI, and we refresh this here, we can actually see our application running. I have to do this a little quickly, and then I can continue talking.

Oh, no, it's not control Is it There it is. Okay, command-control-C you Macs is not fun for me.

So, we had our application running. We said we had our debit ledger. I killed the application cold. So, as you can see here, the running state of this application is gone. We no longer have it. In a traditional system, this would be potentially problematic. We would have to you know, either have saved that state to a database and then re- uh rehydrate it when it comes back online. But, uh with Temporal, that's not really a problem because to the state of our application is stored right here inside of it. So, the very first uh the debit ledger uh function stored the output right here. So, we have a retry policy uh activity task completed. We debited 4,200. So, we have that done. There's nothing running right now, so it's going to start complaining and telling me, "Hey, you have nothing running. Our workflow task has timed out." We have a dead application.

Uh and then we go back to our worker mid-settlement. Whenever we're ready, we can just restart the worker.

And the application picks up as if the if the failure never happened. It rebuilt the entire state of our agent from all of the previous responses. No LLM calls were redone. No previous activities or functions were re-executed. It has picked up the state, replayed the actions, and then pushed it through, and we got the execution to work.

So, why does durability matter for agents? Well, uh your agents are loops. Um there's a lot of things inside of your agents right now that cost a lot of money. Making LLM calls on on a massive scale is not cheap. There's their tokens you have to deal with. There's a lot of failure states. There's a lot of advanced states. Say you get through a really long loop and you know, you're 12 steps in and you lose the entire state of that application. Now you either have you've either had to built basically built a version of Temporal yourself where you are maintaining the state of your application in a database somewhere, and then you have to build all the reconstruction logic and all the retry logic, or uh you can use something like a durable execution system like Temporal, and it will do all of this for you. So, this allows for you to have your agents go offline, fail, your LLM provider can go down, you can lose an entire region in AWS. Doesn't matter when they when those when that compute comes back when those resources come back online, the agents pick up right where they left off at the exact last spot and continue execution. And if it happens quickly enough, if it's a quick enough failure, your user will never even be aware that they that they lost service of this. Um if you had been on the receiving end of this worker call that I had just done where we waited a minute and you were knew you were going to wait a minute for the approval and that failure happened and it happened and I restarted the worker within, you know, 5 seconds of the failure. As a user on the client side, you probably never would even notice that there was this kind of failure and that's what Temporal does. Is it brings it all the way out uh for you and just keeps the execution going forward regardless.

Now, the interesting thing is um the secrets for all of this were actually not inside of our Temporal event history.

So, if we go back to our client over here and we run this command, oop, I hit a button.

Oh, I have to actually put in the correct workflow ID. If I don't, it doesn't work.

If I go back here and collect this workflow ID.

Uh it's on the client tab. Yeah.

And we click the up arrow.

Now, we're going to hope I know how to paste on Mac.

Aha, we got it. Good.

So, we can actually see we actually have a little little Python script here that says that no JWT token uh material uh was basically sent. We didn't like our worker through the entire event history here, um you can see the the starting process and the result. So, if we click in, I can see the debit ledger here with the result down here.

So, we have our uh each individual function is stored there. So, our second function here, mark settled, was also uh settled as well. So, this was the result of it, but nowhere in our workflow if I go to the actual event history, which is this is actually what the event history looks like under the hood, you will not find it anywhere uh because we didn't store it. Um

so, Temporal gives you basically two different ways uh to keep the sensitive data out. So, we have the interceptor, which is what Keycard provided for us. So, they built an interceptor that basically injects it at uh uh keeps the data and the credentials out of it entirely and then injects it back in when it's time to execute. Think of it like almost like just-in-time credentials uh and does that. Or the other thing for Temporal that's really awesome is there's what's called a payload uh encoder. So, what you can do is you saw in our Temporal Web UI, your data was There we go. Wrong button. Your data is just sitting here in nice wonderful plain text.

You have the ability to encrypt this yourself. So, you can basically spin up There's like a There's an entire pattern and library in Temporal. You spin up a sidecar, you create an encryption algorithm, you set what the encryption policy is, and all data that comes to Temporal, whether it's self-hosted or in the cloud, is essentially encrypted. And we can't read it. We don't control your keys. We honestly don't quite care about what you're doing inside of it. That's not the part that we care about. We care about putting all these fancy things in order. So, that's a quick overview of like Temporal and building out it building out agents with it. There's a lot of integrations with Temporal you can try out. There's an Open AI, Pydantic AI.

I know there's LangChain and a whole bunch of other ones too as well.

Um

And I think we even now have like an agentic harness now that we've been building out that's going out too. So, you can come by and see us at our booth if you want to learn more about that. Um

And yeah, so the expense desk, you know, basically we I'll bring him back up to kind of wrap it up and we can take some questions if you want. Building out the agent identity, building out all of the agent worker and all of that stuff, and then Temporal becomes the execution layer to make sure that your agent runs properly and doesn't fail in the case of, you know, any sort of cataclysmic failure, API outage, AWS region just decides it wants to disappear for a day, which does happen. So, yeah, that's all I have.
</details>