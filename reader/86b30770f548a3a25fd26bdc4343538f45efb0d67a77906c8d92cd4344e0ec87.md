---
layout: post.njk
source: https://baoyu.io/blog/2026-02-13/claude-code-auto-commit
speaker: baoyu.io
title: 用 Claude Code 的 Hook + Skill，实现每次提交后自从 commit 提交变更 | 宝玉的分享
date: '2026-02-18'
summary: 本文介绍了一种使用 Claude Code 的 Hook 和 Skill 机制，实现代码变更自动提交的方法。通过在任务结束时触发一个自定义的 `Stop` Hook，脚本会检查工作区是否有未提交的变更。若有，则阻止 Claude Code 结束任务，并调用一个 `/commit` Skill。该 Skill 能够智能分析变更内容，按文章、代码或配置等主题进行分组，并自动生成规范的中文 Commit Message。这一方案旨在提高开发者工作效率，确保 Git 历史记录的清晰和完整性，避免遗漏任何修改。
area: tech-engineering
category: software-development
tags:
  - claude-code
  - git-hooks
  - ai-skills
  - workflow-automation
  - developer-productivity
people:
  - 宝玉
companies_orgs: []
products_models:
  - Claude Code
  - Git
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-02-18

# 用 Claude Code 的 Hook + Skill，实现每次提交后自从 commit 提交变更

作者：

宝玉

我用 Git 管理所有写作内容，文章、素材、提纲、草稿，全在仓库里。问题是我经常忘记提交。写完一篇文章，润色完，发布了，然后就去忙别的了。过几天一看 git status，十几个文件的变更堆在那里，完全不记得哪次改了什么。Git 本来是用来追踪每一步修改的，结果变成了一个大杂烩的快照工具。

现在我用 Claude Code 跑写作流程，从素材分析到成稿发布基本都交给它。既然每次任务它都在改文件，能不能让它改完就自己提交？

两个机制配合就解决了。

## Hook：任务结束时的拦截器

Claude Code 支持 Hook 机制，在特定事件（会话开始、工具调用前后、任务结束等）发生时自动执行脚本。思路和 Git Hook 类似，但挂在 Claude Code 的生命周期上。

我在项目的 .claude/settings.local.json 里配了一个 Stop Hook，每次 Claude Code 准备结束任务时触发：

```
<code class="language-json">"hooks": {
  "Stop": [{
    "hooks": [{
      "type": "command",
      "command": "\"$CLAUDE_PROJECT_DIR\"/.claude/hooks/auto-commit.sh"
    }]
  }]
}
</code>
```

脚本做的事很简单：检查工作区有没有未提交的变更（新文件、修改、删除），如果有，就阻止 Claude Code 停下来，告诉它“你还有活没干完，去提交”。

核心逻辑就这几行：

```
<code class="language-bash">if git diff --quiet && git diff --cached --quiet && \
   [ -z "$(git ls-files --others --exclude-standard)" ]; then
  exit 0  # 没变更，正常结束
fi

# 有变更，拦住它
echo '{"decision": "block", "reason": "检测到未提交的变更，请调用 /commit 技能提交更新。"}'
</code>
```

还有个细节：提交本身也会触发“任务结束”，不处理就无限循环。脚本用 stop_hook_active 标志跳过二次触发。

## Commit Skill：让提交有意义

Hook 只管拦截，具体怎么提交靠 Commit Skill。

Skill 是 Claude Code 的技能模块，放在 .claude/skills/ 目录下，用 SKILL.md 定义工作流程。name 字段自动变成 /slash-command，手动或自动都能触发。相当于一份操作手册，告诉 Claude Code 遇到特定任务该怎么做。

我的 /commit 技能定义了这些规则：

先分析变更文件的路径，判断改的是文章、技能配置还是代码

按主题分组提交，不把所有东西塞进一个 commit。比如改了两篇文章，就分两次提交

自动生成中文 commit message，格式固定：文章用“添加/润色/更新 + 主题”，代码用“优化/修复 + 功能”

明确指定提交文件，避免 git add . 这种粗暴操作，排除临时文件和备份文件

这样 git log 里看到的是：

```
<code>42257b3 添加 Amodei NYT 访谈整理文章
c4eee96 添加 Peter Steinberger OpenClaw 访谈整理文章
e2a01da 润色 Suleyman FT 专访文章
</code>
```

每条都说得清楚这次改了什么，不是那种“update files”或者“misc changes”的垃圾信息。

两个机制的配合：Hook 当守门员，保证没有变更被遗漏；Skill 当执行者，保证每次提交都有意义。 我再也不用惦记提交这件事了。

## 附录：完整配置

### Hook 脚本

文件路径：.claude/hooks/auto-commit.sh

```
<code class="language-bash">#!/bin/bash
# Stop hook: 任务完成后自动检测未提交变更并触发 commit skill

INPUT=$(cat)
STOP_HOOK_ACTIVE=$(echo "$INPUT" | jq -r '.stop_hook_active // false')

# 防止无限循环：commit 后再次触发时直接放行
if [ "$STOP_HOOK_ACTIVE" = "true" ]; then
  exit 0
fi

# 检查是否有未提交的变更
cd "$CLAUDE_PROJECT_DIR" 2>/dev/null || exit 0

# 检查工作区是否有变更（已修改、新文件等）
if git diff --quiet 2>/dev/null && git diff --cached --quiet 2>/dev/null && [ -z "$(git ls-files --others --exclude-standard 2>/dev/null)" ]; then
  # 没有变更，正常结束
  exit 0
fi

# 有未提交变更，阻止 Claude 停止，让它继续执行 commit
cat <<'EOF'
{"decision": "block", "reason": "检测到未提交的变更，请调用 /commit 技能提交更新。"}
EOF
</code>
```

### Commit Skill

文件路径：.claude/skills/commit/SKILL.md

```
<code class="language-markdown">---
name: commit
description: 提交当前未 commit 的修改。自动分析变更内容，生成规范的 commit message，支持按目录分组提交或一次性提交所有修改。
---

# Git Commit 技能

提交当前未 commit 的修改到 git 仓库。

## 工作流程

### 步骤一：查看未提交修改

git status --short

分析变更类型：
- M - 已修改
- ?? - 新文件（未跟踪）
- D - 已删除
- R - 重命名

### 步骤二：分析变更内容

根据修改文件路径判断变更类型：

| 路径模式 | 变更类型 |
|----------|----------|
| posts/YYYY-MM-DD/[slug]/ | 文章相关 |
| .claude/skills/ | 技能配置 |
| src/ | 脚本代码 |
| .r2-upload-map/ | 资源映射（通常不单独提交） |
| 其他 | 项目配置 |

### 步骤三：决定提交策略

单一主题修改：一次性提交所有文件

多主题修改：按目录/主题分组提交

分组优先级：
1. 文章目录（每篇文章一个 commit）
2. 技能目录（每个技能一个 commit）
3. 代码变更（合并为一个 commit）
4. 配置文件（合并为一个 commit）

### 步骤四：生成 Commit Message

格式规范：
- 用中文
- 简洁描述变更内容
- 不超过 50 字

常用模板：
- 文章：添加 [文章主题简述]、润色 [文章标题]、更新 [文章标题]
- 技能：添加 [技能名] 技能、更新 [技能名] 技能
- 代码：优化 [功能描述]、修复 [问题描述]
- 配置：更新项目配置

### 步骤五：执行提交

git add <file1> <file2> ...
git commit -m "commit message"

注意：
- 避免使用 git add . 或 git add -A
- 明确指定要提交的文件
- 排除临时文件（.bak-*、.html.bak-*）

### 步骤六：确认结果

git log --oneline -3

输出最近提交记录确认成功。

## 排除规则

以下文件默认不提交：
- *.bak-* - 备份文件
- .DS_Store - macOS 系统文件
- node_modules/ - 依赖目录
- .r2-upload-map/*.json - 通常随文章一起提交，除非单独要求
</code>
```

### Hook 配置

文件路径：.claude/settings.local.json（相关部分）

```
<code class="language-json">{
  "hooks": {
    "Stop": [{
      "hooks": [{
        "type": "command",
        "command": "\"$CLAUDE_PROJECT_DIR\"/.claude/hooks/auto-commit.sh"
      }]
    }]
  }
}
</code>
```

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme