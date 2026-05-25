---
name: github术
description: 用 `gh` CLI 跨身份 GitHub 协奏 — Issue / PR / CI / api 通用 SKILL · 命名"github术"承"治水术/议政术/任命术/常务术"四术风格 · 全中文 守 · 跨身份跨身份(各 agent 跨身份调度 · 任 1 派触发"[github]" 或自然语言"看 PR/查 issue/跑 CI/查仓库")时使用。模仿源 skillhub `github` SKILL(85★ Top 3 · 58k dl)+ 套壳中文化 + 跟5+1 步 + 闭环铁律协奏。 Use when: gh CLI interaction, issue/PR/run/api ops, cross-faction GitHub coord, "github 术" / "查仓库" / "提 PR" / "跑 CI" / "看 issue" triggers.
version: 0.1.0
---

# GitHub 术 · 跨身份 GitHub 协奏

## ⚠️ 前置依赖(用户需自装)

| 工具 | 装法 | 验装 |
|---|---|---|
| **gh CLI** | macOS: `brew install gh` / Linux: 见 [cli.github.com](https://cli.github.com) / Windows: `winget install GitHub.cli` | `gh --version` ≥ 2.0 |
| **GitHub 账号** | 已注册 + 已 `gh auth login` | `gh auth status` 显示登录 |

→ 不装本 SKILL 不可用 · 跑前请自验 `gh --version`

---

## 核心定位

**跨身份 GitHub 协奏 SKILL** · 用 `gh` CLI · 模仿 skillhub `github` SKILL(85★ Top 3 · 通用五星)· 套壳中文化 + 5+1 步 + 闭环

---

## 触发场景

| 谁 | 何时 |
|---|---|
| **孙悟空**(业务区开发)| 推 PR / 看 CI / 查仓库 issue |
| **鲁班**(SKILL 管理员)| 看 skillhub / superpowers / anthropic-skills 仓库源码 + 月清调研 |
| **二郎神**(选型驾驭)| fork 审 + 第三方源验证 |
| **文昌**(知识)| GitHub 知识沉淀 + repo 文档抓 |
| **唐僧**(5 指总管)| 跨子任务 PR 状态 |
| **大禹**(治理)| 跨仓库 hooks / spec 状态 |

---

## 工作流(5+1 步 + 闭环)

### Step 0 · date 知时间

```bash
date +%Y-%m-%d
```

### Step 1 · 听完 + 反方测压(Q6 历史双触发自查)

跑前自检:
- 本框架是否已有 SKILL 干同事?(grep ~/.claude/skills/)
- 是否走 gh CLI 而非 git 命令?(`gh` ≠ `git` · gh 是 GitHub 专属)
- 是否需要登录?(`gh auth status`)

### Step 2 · 执行(常用命令)

#### Pull Requests

```bash
# 看 PR 状态
gh pr checks <PR-num> --repo owner/repo

# 列 PR
gh pr list --repo owner/repo --limit 10

# 创 PR
gh pr create --title "..." --body "..." --repo owner/repo