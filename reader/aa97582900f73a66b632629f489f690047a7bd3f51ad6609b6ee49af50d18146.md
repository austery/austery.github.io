---
layout: post.njk
source: https://yage.ai/share/ai-builder-static-site-hosting-guide-20260719.html
speaker: yage.ai
title: AI 做完了一个网页，下一步该放到哪里？
date: '2026-07-19'
summary: 文章探讨了AI生成网页后，如何进行部署和发布的问题。核心在于判断页面是否需要后台，并根据需求选择合适的托管方案，如Cloudflare Workers、Vercel、Koyeb或VPS等，以平衡静态页面的交付便捷性与动态功能的需求。
area: tech-engineering
category: deployment
tags:
  - static-hosting
  - web-deployment
  - cloudflare-workers
  - vercel
people: []
companies_orgs: []
products_models:
  - Cloudflare Workers Static Assets
  - Vercel
media_books: []
draft: true
status: evergreen
---

AI Builder
经常会做出一些介于文档和产品之间的东西：一套可以在浏览器里播放的 slide
deck，一个活动 landing page，一份交互式报告，或者用来验证想法的小型
demo。AI
很快就能把页面做出来，真正要发给别人时，却还差一个所有人都能打开的链接。

从本机上能打开，到别人点链接也能看到，中间还隔着几件事：网页要放到公网可以访问的地方，要有
HTTPS，内容修改以后还得能顺利更新。页面虽然已经做好了，这些发布工作总要有人处理。

Cloudflare、Vercel、Koyeb 和自己的 VPS
都能给出这样一个链接，接手的工作却不一样。有人替你保管网页和处理访问流量，有人把每次代码修改也接进发布流程，也可以全部留给自己的服务器。

比较这些方案之前，先要判断页面是否真的需要后台。纯静态网页已经是可以直接交付的成品，浏览器下载后就能显示，不需要服务器现场计算。我越来越觉得，AI
降低网页制作成本以后，发布环节最常见的浪费，就是为一个没有后台的页面引入长期后台。

## 纯静态页面，先在
Cloudflare 和 Vercel 之间选

先看访客打开页面时会发生什么。

计算公式、渲染图表、播放幻灯片等操作如果都在浏览器内完成，这就是纯静态网页。浏览器下载
HTML、CSS、JavaScript
和图片后在本地执行，不需要云端计算或数据库，静态文件分发平台就能完成托管。

需要写入数据或调用敏感 API 时，边界就变了。例如使用远程数据库
Turso，不能把密钥写进前端
app.js。任何访客都能查看浏览器收到的代码，拿到密钥后便可能读写数据库。这类操作需要可信后端代为执行。

同一个静态网页文件夹通过四条路径获得公开链接

确认页面不需要后台以后，选择会简单很多。只想尽快获得可分享的 HTTPS
链接，可以直接使用 Cloudflare
Workers Static Assets。

上传后，Cloudflare
会把文件复制到全球节点并缓存。访客打开链接时，较近的节点直接返回文件。只要请求匹配静态资源，默认就不会执行
Worker 代码，因此没有服务器休眠和冷启动等待。

根据 Cloudflare
Workers
计费文档，静态资产请求免费且不限量，也不收流出流量费。文件可以通过控制台拖拽、Wrangler
或 GitHub 发布。对访问量不确定、又要长期在线的 landing page 和 slide
deck，这是最省心的默认选择。

项目需要多人修改和确认效果时，Vercel 的优势更明显。Cloudflare
解决的是把成品稳定地放上网，Vercel
则把代码修改、预览和正式发布连成了一条 Git 工作流。

Vercel 是 Next.js 背后的公司，所以把两者联系在一起很自然。但使用
Vercel 并不需要先把项目改成 Next.js。框架支持说明列出了
Vite、Astro、SvelteKit 等多种选择。即使项目没有使用任何框架，部署指南和构建配置文档也允许跳过构建，直接发布静态文件；Vercel
Drop 还支持在网页里拖入文件夹。

真正拉开差距的是 Git 协作。每次提交或 Pull Request 都可以生成独立的
Preview URL，合作者在合并前就能打开成品，改错后也能快速回滚。Vercel
Functions虽然会在没有请求时缩容至零，但静态页面根本不运行
Function。选择 Vercel 的主要理由是预览和版本管理，不是休眠机制。

## 为了后端，或者利用已有服务器，再看
Koyeb 和 VPS

页面接下来要增加 Python、Node.js 后端或 WebSocket 长连接，Koyeb
可以把前后端留在同一个运行环境里。

Koyeb 并非专门的静态文件平台。服务参考文档显示，它管理实例上持续运行的
Web Service；平台对比说明则说明
CDN 也会放在这些服务前面。托管静态页面时，容器内仍有 Nginx
或应用进程响应请求。

实例空闲后可以按照 scale-to-zero
规则停止。Deep Sleep 唤醒通常需要 1 到 5 秒；Light Sleep
利用快照把时间缩短到约 200
毫秒，但仍处于公开预览阶段。纯展示页让访客等待这几秒没有必要。后端很快就会上线时，统一部署才会抵消这份额外成本。

另一种情况是 VPS 已经在那里。VPS 是自己管理的 Linux
虚拟服务器。服务器已经承载其他业务时，用 Nginx
增加一个静态目录通常不会明显增加计算账单。Nginx
入门指南中的基础用法，就是从本地目录返回网页和图片。路径、响应头和访问日志也都由自己控制。

专门为了分享一个网页新开 VPS，则是另一笔账。除了租金，还要配置
Nginx，参照 Certbot
官方教程申请 HTTPS 证书，设置自动续期并用
certbot renew --dry-run
验证。此后的系统补丁、监控、备份和故障恢复也由自己负责。软件免费，不等于无人运维。

## 一分钟选择

纯静态页面：默认选 Cloudflare Workers Static Assets，没有服务器和冷启动，也不用承担静态请求与流量费。

团队频繁 review：选 Vercel，把 Preview URL 和回滚放进 Git 工作流。

即将增加完整后端：选 Koyeb，接受实例生命周期，换取容器和完整运行时。

已有常驻服务器：选 Nginx，利用接近于零的边际计算成本，同时继续承担 VPS 运维。

最后一条边界比平台选择更重要：网页一旦需要 Turso
或第三方服务的敏感凭证，就不能再把所有逻辑留在浏览器里。先加一层可信后端，再讨论它应该运行在哪里。