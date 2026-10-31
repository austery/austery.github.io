---
layout: post.njk
source: https://yage.ai/share/codex-ssd-write-bug-20260623.html
speaker: yage.ai
title: |-
  OpenAI Codex 静默往用户 SSD 年化写入 640
  TB，已逼近消费级硬盘额定寿命
date: '2026-06-25'
summary: OpenAI Codex CLI 在后台向用户本地 SQLite 日志库持续写入数据，导致年化写入量逼近消费级 SSD 的额定寿命。该问题源于日志级别默认设为 TRACE 且写入频率放大导致的写放大现象，使得文件系统层面的检查（如 du）与硬件层面的寿命计数器（SMART）出现脱节，使问题长期未被发现。
area: tech-engineering
category: ai-application
tags:
  - ssd-write-wear
  - sqlite-logging
  - write-amplification
  - smart-monitoring
people: []
companies_orgs:
  - OpenAI
products_models:
  - Codex CLI
media_books: []
draft: true
status: evergreen
---

外表完好的 SSD，内部 NAND
芯片在无声崩坏

OpenAI Codex CLI 被发现长期静默往用户本地 SQLite 日志库写入数据，21
天累积 37 TB，年化约 640 TB，逼近一块 1TB 消费级 SSD 的额定写入寿命。4
月 10 日就有人首次报告这个问题，6 月 22 日登上 Hacker News 前排后 The
Register 做了跟踪报道，标题直言这类无效写入 costing millions。6 月
23 日 OpenAI 合并了修复 PR、关闭了 issue，但修复并不完整：当日另一份
issue 显示 Windows 桌面包在修复合并后仍然复现，第三项关键修复仍在
0.143.0 里没有发布。

## 这跟我有没有关系

先说这个 bug 长什么样。Codex 在后台持续往本地一个 SQLite
日志库写入运行数据，量大到能在不到一年里烧穿一块消费级 SSD
的额定写入寿命。它不会让磁盘空间变满（日志会被自动回收），不会让程序报错，也不会触发任何系统告警。你唯一可能察觉到的异常是硬盘灯常亮、磁盘活动频繁。代价全落在
SSD 的写入寿命这个指标上，而它从不出现在任何日常的磁盘检查里。

所以谁受影响：在用 Codex CLI
并且让它常驻运行的人，硬件在被直接消耗；用 Claude Code 或 OpenCode
的基本不受影响。如果你是 Codex 用户，往下看版本和自检。

先看版本。升到 0.142.0
或以上是分水岭，这个版本合并了修复，据报告者反馈能砍掉约 85%
的日志写入。但修复还没全部到位：还有一项修复在 0.143.0 里没发布，而
Windows 桌面包在修复合并之后仍然能复现（issue
#29556）。升到 0.142.0
能解决大部分问题，但没到一个版本号就完全干净。

要确认到底往这块盘上写了多少，查 SMART 计数器，而不是看磁盘空间。du
和 Finder 看到的是文件大小，SMART 读到的才是物理写入量。macOS 上安装
smartmontools（brew install smartmontools），运行
sudo smartctl --all /dev/disk0，找
Percentage Used 和 Data Units Written。Linux
NVMe 跑 sudo nvme smart-log /dev/nvme0。Windows 上跑
Get-PhysicalDisk | Get-StorageReliabilityCounter，或用
CrystalDiskInfo 图形工具。

来不及升级的话有三条临时手段。把 ~/.codex/logs_2.sqlite
符号链接到 /tmp，让写入落到内存而非硬盘。在数据库里加一条
trigger
拦掉所有插入：CREATE TRIGGER block_log_inserts BEFORE INSERT ON logs BEGIN SELECT RAISE(IGNORE); END;，代价是丢掉本地诊断日志。定期跑
VACUUM 回收空间，有人从 27 GB 压回了 73 MB。Codex
没给这个日志留官方开关，config.toml 里没有
sqlite_logs_enabled 这类选项。

## 为什么会出现这个问题

Codex 把运行日志写进 ~/.codex/logs_2.sqlite，一个本地
SQLite 数据库。SQLite
单文件、零配置，桌面应用拿它做本地存储是常规操作。问题出在 Codex
决定往里写什么、以什么频率写。

日志级别默认设成了 TRACE。在 Rust 的 tokio-rs/tracing 库里，TRACE
是比 DEBUG
还低一级的级别，会把程序运行中每一次文件打开、每一条网络报文原封不动地输出。Codex
连打开 /etc/passwd 这种系统文件、WebSocket
原始帧都记了下来。它的配置方式是
Targets::new().with_default(Level::TRACE)，一个每层过滤器。用户把
RUST_LOG=warn 设好，以为全局生效了，但只要某个 target
没被显式覆盖，Codex 的默认值就照写不误，绕过了环境变量的配置。

写入频率放大了问题。SQLite 默认的 WAL（Write-Ahead
Log）模式把每次写入先追加到一个日志文件里，攒够了再合并回主库。Codex
持续插入新行、同时删掉旧行，维持总行数不变。在一个观测窗口里，15
秒内插入了 36,211 行，数据库文件大小纹丝不动，因为 SQLite
在后台回收了旧空间。不过这不等同于没有物理写入。每条 INSERT 都会变成
NAND 扇区上的实际写入，DELETE
操作也产生额外写入。这个差距叫写放大：应用层写一行，物理层可能写了三倍、五倍的数据量。

落到硬件上。三星 990 PRO、WD SN850X、Crucial P5 Plus 这类 1TB 消费级
NVMe SSD，额定写入寿命普遍标在 600 TBW（Total Bytes
Written）。据报告者、Apache Flink PMC 成员 Rui Fan 的测量，他那台机器 24
小时常驻 Codex，21 天写入 37 TB，年化 640
TB，不到一年就烧穿这条保修线。换成每天用 8 小时的重度用户，一年约 213
TB，大概三年烧穿，仍远高于正常开发工作负载。修复后降到每年约 32
TB，回到普通水平。600 TBW 是保修值，不是到了就坏的硬边界，很多盘超过 TBW
数倍后仍能正常使用。截至发稿，没有公开的因这个 bug
实际烧坏硬盘的案例。

## 为什么那么长时间没人发现

这件事从 4 月活到 6
月才引爆，核心原因是文件大小和物理字节写入跑在两个不同的时钟上，整套检查磁盘的默认工具读的都是错的那个。

du、df、Finder、磁盘容量告警，这些工具读的全是文件系统层的逻辑大小：文件占了多少个块、还剩多少块空闲。SSD
的寿命跑在另一个时钟上。NAND
闪存的写入-擦除循环有次数上限，每次物理写入都在消耗这个额度，只有硬盘自己的
SMART 计数器能读到。Percentage Used
记录已用掉了多少百分比的额定寿命，Data Units Written
记录累计向 NAND 实际写入了多少数据。

Codex 这个 bug 恰好藏在两个时钟的缝隙里。SQLite
一边狂写一边回收空间，数据库文件大小保持稳定。du
看过去，这个文件不大，也没有持续膨胀，一切正常。物理写入计数器却在另一个维度上飞速转动。盯着
du 三个月看不出问题，换成 SMART 一眼就能看见在烧。

issue
#17320 在 4 月 10 日就给出了完整的技术证据：5 到 16 MiB/s
的持续写入，strace 里 pwrite64
刷屏。但每个读到这份报告的人都用检查磁盘的默认习惯去评估，看
du、看剩余空间，得出一个在当时看来合理的结论：文件体积稳定，磁盘没满，不构成紧急问题。这个结论一直站到
6 月 14 日，Rui Fan 在 issue #28224
里贴出 SMART 数据，年化 640 TB 的数字才正式摆在公众面前。6 月 22 日登上
Hacker News 前排，The Register 跟进报道，第一个修复 PR
当天创建并合并。

文件系统关心空间够不够用，SMART
关心盘还能撑多久。日常运维习惯只盯前者，这个 bug
就在两者之间的盲区里活了下来。

下一次你的机器风扇不转但盘灯常亮，打开 SMART
看一眼。那三行命令在每一台机器上都能跑。