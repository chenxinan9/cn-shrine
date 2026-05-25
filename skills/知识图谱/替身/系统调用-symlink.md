---
替身编号: TS-知识图谱-001
借用者: Claude Code 系统(自动调用)
借日: 2026-05-25 04:52
替身类型: symlink(系统装机入口)
真物路径: 本目录 SKILL.md(主源)
symlink 路径: ~/.claude/skills/知识图谱 → 本目录
---

# 替身 · Claude Code 系统调用 symlink

## 这是什么

Claude Code 系统在 `~/.claude/skills/` 扫描可用 SKILL · 但**真文件已搬到藏经阁** · 所以原位是 symlink 替身。

## 验证(2026-05-25 04:52)

```bash
$ ls -la ~/.claude/skills/知识图谱
lrwxr-xr-x ... 知识图谱 -> ~/Desktop/藏经阁(知识库)/SKILL总库/02-思维类/知识图谱

$ head -1 ~/.claude/skills/知识图谱/SKILL.md
# 透 symlink 真读到主文件 ✅
```

**关键发现**: Claude Code **完全支持 symlink SKILL** — 系统重新加载后,"知识图谱" 仍在可用 SKILL 列表 + description 全文还在。

## 调用方

| 调用方 | 频率 | 借因 |
|---|---|---|
| **Claude Code 系统** | 每次会话启动扫 | 让 AI 自动可调本 SKILL |
| **本朝 AI**(任何派) | 自动触发(description 匹配) | "记住 X / X 跟 Y 啥关系 / [知识图谱]" |

## 不能动

- ❌ 不擅 rm ~/.claude/skills/知识图谱 symlink(等于让本 SKILL 离线)
- ❌ 不擅 mv 藏经阁真文件(symlink 会断)
- ✅ 真要改 SKILL.md → 直接改藏经阁真文件 + 立即 cat ~/.claude/skills/知识图谱/SKILL.md 验同步

## 恢复 SOP(若 symlink 坏了)

```bash
# 若 ~/.claude/skills/知识图谱 symlink 坏 → 重建
ln -sf "$HOME/Desktop/藏经阁(知识库)/SKILL总库/02-思维类/知识图谱" "$HOME/.claude/skills/知识图谱"
```

## 原源备份位置(不擅 rm · )

`~/.claude/.trash-skills-20260525/知识图谱-mv于0525/`

候 30 天观察无问题 → 可清理(报盘古候决)
