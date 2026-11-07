---
layout: post.njk
source: https://yage.ai/share/mcp-elicitation-human-in-loop-20260716.html
speaker: yage.ai
title: |-
  MCP 为什么需要
  Elicitation：工具执行到一半，如何把人带回来
date: '2026-07-16'
summary: 本文探讨了MCP（Model Context Protocol）在AI工具调用中如何实现'elicitation'机制，即当远程服务器发现任务执行过程中存在信息缺口时，暂停任务并向用户请求补充信息。文章详细阐述了通过'form'模式收集结构化输入和'URL'模式处理敏感流程的不同数据路径，以及客户端（host）在不同层级对用户交互的权限控制差异，强调了协议设计与实际客户端体验之间的差距。
area: PAI
category: ai-tooling
tags:
  - agentic-workflow
  - elicitation
  - form-mode
  - url-mode
  - client-experience
people: []
companies_orgs: []
products_models: []
media_books: []
draft: true
status: evergreen
---

MCP 给 AI
应用和外部工具规定了一套标准连接方式，但普通工具调用里藏着一个前提：client
发出请求时，server
已经拿到了完成任务所需的全部参数。真实业务很少这么规整。工具查过数据后，才可能发现需要用户选择转机方案、补充业务信息，或者去第三方系统完成授权。

麻烦在于，发现缺口的是远端 server，界面却掌握在用户操作的 host
手里。server
不能自己弹出窗口，也不能假设模型一定能从一条报错里还原它想问什么。MCP
因此需要一条反向通道：server 暂停当前任务，通过 client
把结构化问题交给用户；用户处理完，结果回到原来的
server，任务带着已有状态继续。这套设计就是 elicitation。

这里要解决的比多弹一个对话框更复杂。server
发出请求后，当前任务要先停在原地。用户可以补充信息，也可以拒绝或取消；client
把结果送回去，server 再从原来的位置继续。MCP
需要为这些动作规定统一的信息格式和返回路径。MCP 在 2025-06-18
版规范中加入了 form 模式的前身，又在 2025-11-25
版加入 URL
模式。两种模式分开，是因为普通偏好、账户授权和支付凭证不能沿着同一条数据路径传递。

这也决定了理解 elicitation 的重点：为什么 server
不能让模型随口再问一句，为什么 form 与 URL 必须分开，为什么 server
的业务确认不能代替 host 权限，以及 client
怎样把暂停的任务接回来。Cloudflare 在 2026
年补上的客户端处理能力，只是这套协议设计进入真实产品的一处新进展。

一次 elicitation
的完整往返：正常工具调用抵达远端 server，server
发现信息缺口后暂停任务，经 MCP client
询问用户，再收到响应并继续执行

## Server
为什么不能让模型自己再问一句

例如，用户让 agent 预订下周去东京的机票。负责查票的旅行 server
先找到航班，随后才发现需要用户选择转机方案；继续处理折扣时，又需要用户去第三方系统授权常旅客账户；到了付款环节，还要进入独立的支付流程。转机偏好、账户授权和支付信息不可能全部塞进最初那次工具调用。

这里的 server 是 Model
Context Protocol（MCP）连接中的外部工具。用户实际操作的 AI 应用叫
host；host 里的 client 维护着与这个 server 的连接。server
能查航班、算价格，却没有 host 的界面，也不能自行决定 host
的全局权限。它发现问题后，需要一条标准途径把问题交还给 client。

没有 elicitation，server
通常只能报错，让模型猜出报错背后的问题，再重新询问用户；或者返回一个没有明确用途的链接；再不然，每个
server 都为不同 client
自建回调。前两种做法容易打断任务，模型可能要重新规划，甚至丢掉前面已经查到的状态。后一种做法则让每组产品都维护一套私有接口。

elicitation 让 server
发出结构化请求，并在原地等待。用户回答后，client 把结果送回发起请求的
server，后者带着已有状态继续处理。协议由此规定了任务从暂停到继续执行的完整往返，不再只定义最初的工具调用。

## Form 和 URL
分开的原因是数据去哪里

MCP
为这类请求安排了两条数据路径。选择哪一条，先看用户要交出的是什么信息，以及这些信息能不能经过
MCP client。

form 用来收集非敏感的结构化输入。server 可以请
client 显示输入框、选项或确认按钮，用户填写后，数据经 MCP client 返回
server。Cloudflare 早在 2025
年 8 月 5 日就支持 server
发起这类表单请求。协议同时划出一条明确边界：密码、API
密钥、访问令牌和支付凭证都不能通过 form 索取。

遇到 OAuth、支付等敏感流程，server 改用 URL。client
先向用户展示外部链接，用户同意后，再由浏览器或其他外部环境打开安全页面。机密信息留在第三方流程里，不进入
MCP client 或模型上下文。这里的 accept 只表示用户愿意打开链接，不代表
OAuth 已授权、账户已绑定或款项已支付。MCP client 访问 server
的鉴权，和第三方 OAuth 也属于两套独立流程。

一次机票任务中的三种暂停：普通偏好走 MCP
Form，第三方授权走 MCP
URL，最终敏感动作仍由独立权限或支付系统把关

图里三次暂停的外观可以一样，数据却走向不同地方。转机偏好经 form
返回旅行 server；常旅客账户在外部页面完成
OAuth；付款仍由支付系统自己把关。客户端如果只会“弹一个框”，却说不清来源和数据去向，就没有完整实现这项协议能力。

## 看起来都是弹窗，谁在请求完全不同

同一个确认按钮，在不同层里表达的权力并不一样。host 为工具调用设置的
allow、ask、deny 规则，是保护本地环境的强制关卡。OpenCode 的权限机制和 Claude Code 的
hooks都把这类检查放在宿主侧。第三方 OAuth
与支付则由外部业务系统执行。server 自己发出的 form 或 URL
请求，只能处理自己的业务流程。

机制

发起者

用户决定什么

响应去向

强制执行方

本地问题

模型或本地环境

需求、偏好或歧义

本地环境

不是强制关卡

MCP form / URL elicitation

外部 MCP server

缺失输入或是否同意跳转

发起该请求的 MCP server

server 业务逻辑

host tool permission

宿主策略

既定工具调用能否执行

本地权限引擎

host 宿主环境

第三方 OAuth / payment

外部业务系统

授权身份或确认支付

独立安全服务

第三方系统

假设 server 用 form 问用户是否确认删除文件。用户点了同意，只完成了
server 的业务确认。真正执行删除前，host
仍然可以按自己的权限规则拦下工具。反过来，用户接受一个 OAuth
URL，也只是同意离开当前界面去做身份授权，并没有给本地工具新增执行权。

只看弹窗样式，很容易把“我愿意继续业务流程”误读成“我授权系统执行任何动作”。客户端必须把发起方和作用范围讲清楚，不能用一个通用的“允许”按钮抹平这些差别。

## 协议已经有了，Client
体验仍然不齐

MCP
已经定义了反向请求，但协议存在不等于用户就能完成这段交互。Cloudflare 在
2026 年 7 月 13 日更新
Agent SDK，让 Cloudflare Agent 可以作为 MCP client 处理 form 和 URL
请求。这次更新没有改变 elicitation 的设计，只说明实现缺口已经从 server
能否发问，移到了 client 能否正确处理请求并恢复任务。

client 与 server 建立连接时，会互相声明支持哪些可选能力。client
没有声明 elicitation，server 就不该向它发这类请求。因此，能调用 MCP
工具不等于能处理工具中途发来的问题。

截至 2026 年中，VS Code 的 URL
支持与表单界面更新、GitHub
Copilot Chat、同时处理两种模式的 Kiro、Claude
Code 命令行和 Codex，都有
form 与 URL 支持的直接证据。Cursor 明确支持
form，公开材料尚不足以确认 URL 支持。OpenCode
当时的实现也没有宣告 elicitation。Claude Code 命令行已经支持，不代表
Claude Desktop 或 Cowork 同步具备相同能力。

Cloudflare 的更新还说明了另一个容易混淆的地方。server 侧 SDK 提供
elicitInput()，方便开发者发起请求；client 侧配置
configureElicitationHandlers({form,url}) 后，接收的仍是标准
MCP elicitation/create 请求，并非 Cloudflare
的私有协议。

处理器也不会自动变成完整的用户界面。host 仍要告诉用户哪个 server
正在提问，安全地展示 URL，区分 accept、decline 和
cancel，把结果送回正确的请求，并在操作结束后恢复原任务。MCP
规定了线上传什么数据，没有规定按钮放在哪里、提示词怎么写。客户端体验的差距，就留在这段从协议消息到真实交互的距离里。

同样的对话框外观背后，模型补问、MCP
Server 请求、Host
权限审批和第三方授权拥有不同的发起者、数据路径与执行权

## 其他协议也会等人，但暂停的对象不同

其他 agent 协议也有“停下来等人”的设计，只是各自暂停的对象不同。AG-UI连接 agent
后端与用户前端，它的 interrupt/resume 最接近 MCP elicitation，但覆盖的是
agent 与前端之间的交互。ACP连接编码
agent 与编辑器，关注本地工具能否执行。A2A协调远端 agent
任务，定义了 input-required、auth-required 等状态，却没有提供通用的
elicitation 表单与结果格式。

Microsoft
的 human-in-the-loop和 OpenAI
的 MCP approval主要拦截 host 或运行时中的工具执行。UCP 与 AP2
处理商业和支付授权。这些机制都会等待用户，但不能因为界面相似就互相替代。

## 成熟的 Agent
不会把每一步都交还给人

server
能主动找人，也会带来新的坏用法：开发者可能把每个不确定项都变成弹窗，让
agent 退化成一台确认机器。elicitation
应留给工具启动后才发现的信息缺口、必须在外部完成的安全流程，以及会显著改变业务结果的选择。默认值能安全推断的事项、低风险读取和可逆操作，仍应由
agent 自己完成。

2026 年候选规范的传输细节还可能调整，server
在执行中请求输入的需求却不会消失。判断一个 client 是否真正支持
elicitation，可以看四件事：用户能否看见请求来自哪个
server；数据是否走了合适的 form 或 URL 路径；界面是否准确表达
accept、decline 和
cancel；处理结束后，原任务能否带着正确状态继续。把人叫回来不难，难的是让他在正确的位置做出正确范围内的决定，然后让任务接着走。