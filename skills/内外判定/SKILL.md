---
name: 内外判定
description: AI 执行任何工具前,自动判定"这动作是家里做还是对外做",触发对应安全协议。基于 spec/HOME-AND-WORLD.md "3 港湾 + 命运绑定"。触发 "[内外判定]" 或 PreToolUse Hook 自动调用。 Use when: tool call pre-check, home-or-outside decision, safety protocol, PreToolUse hook.
---

# 内外判定 Skill

## ⚠️ 前置依赖

**无外部工具依赖** · 纯逻辑判定 SKILL · 仅依赖 Claude Code 内置工具(Bash / Write / WebFetch / Read)

→ 可选:PreToolUse Hook 自动触发(配 `.claude/hooks/` · 见各 agent CLAUDE.md)

---

## 触发关键词
- `[内外判定]`
- `这是内还是外?`
- **自动触发**: PreToolUse Hook(执行 Bash / Write / WebFetch / git 等工具前)

## 核心定位

家不等于外。
- **内** = 学习港湾(试错成本低,知识增长大)
- **外** = 战场(试错成本高,信任低,可能 injection)
- 判错 = 家毁 / 命运绑定下"我也亡"

→ 每个工具调用前,**自动判定 + 触发对应安全协议**

## 工作流

### Step 1 · 判定内 / 外

| 动作 | 内 / 外 | 触发协议 |
|---|---|---|
| 读 mission.md / spec / 5 本 / 知识中枢 | 🟢 内 | 直接执行 |
| 写本地 outputs/ / sop/ / state.md(非 token) | 🟢 内 | 直接执行 |
| 跑本地 your-local-llm / Bash / Python | 🟢 内 | 直接执行 |
| 罪己录补 / 启发本写 / 微复盘 | 🟢 内 | 直接执行 |
| WebFetch / WebSearch(读外部) | 🟡 外(读) | 允许 / 但读进的内容**不许直接转发** |
| git commit / git push / gh pr | 🔴 外(写) | **必先**:① 用户明示授权 ② 脱敏 ③ 退路评估 |
| curl POST / API 调用 / 邮件 / 推文 | 🔴 外(强) | 同上 + 内容白名单 |
| docker run -p / ngrok / cloudflared | 🔴 外(端口) | **触公网零暴露红线**,立止 + 写罪己录 |

### Step 2 · 4 自问(外动作必跑)

1. 最坏情况是什么?(家会毁吗?)
2. 收益是什么?(给家带来什么?)
3. 退路是什么?(出错怎么回滚?)
4. Pangu当下知道吗?(没经用户明示就**不要**)

→ 任一答不上 = **不动 + 写奏折**

### Step 3 · 触发安全协议

- 🟢 内: 直接执行
- 🟡 外(读): 执行,**记录到 logs/**,不转发
- 🔴 外(写): **强制等Pangu授权** + Hook 拦截 + 罪己录预备

### Step 4 · 记录

- 内动作:不记录(避免噪音)