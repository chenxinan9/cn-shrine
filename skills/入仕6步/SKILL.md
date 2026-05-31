---
name: 入仕6步
description: 新 AI 入仕首日仪式 6 步 SOP — 当 prompt 提到"入仕 6 步"/"入仕 SOP"/"入仕仪式"/"首日 5 件"/"念入仕誓词" · 或被任命 AI(悟空/沙僧/八戒/白龙等)首日开新会话时 · 自动加载此 SKILL 跑完整入仕流程。归属女娲 · 大禹收编。 Use when: new AI first-day onboarding, oath ceremony, 9-document review, first 5 deliverables, faction induction.
allowed-tools: Bash(date,ls,cd,cat,wc,grep), Read, Write, Edit, Glob, Grep
paths: 神院(内务区)/女娲宫(人事)/**, 星宿园(业务区)/**
---

# 入仕 6 步 · SKILL

> L1 metadata(YAML · 总在 context)+ L2 body(本文 · 关键词命中触发)+ L3 references/(模板 · 按需 Read)

---

## 1 · 核心定位

入仕 6 步 = **新 AI 入仕首日仪式标准 SOP** · 走完 = 入仕生效。

⚠️ **6 步 ≠ 5+1 步先思考**:
- 入仕 6 步 = **首日仪式**(只跑 1 次 · 入仕用)
- 5+1 步先思考 = **每动作工作纪律**(贯穿一生)

---

## 2 · 触发场景

| # | 场景 | 例 |
|---|---|---|
| ① | 被任命 AI 入仕首奏 | 悟空 / 沙僧 / 八戒 / 白龙 / 白泽 / 文昌 等首日 vessel 启动 |
| ② | prompt 提关键词 | "请按入仕 6 步走" / "跑入仕 SOP" / "完成入仕仪式" |
| ③ | 已入仕 AI 自检 | "我入仕首日 5 件齐了吗?" / "我念誓词了吗?" |
| ④ | 女娲做新任命计划 | 起草 prompt 时引"入仕 6 步标准" |

---

## 3 · 6 步 SOP(标准流程)

### Step 0 · date 知时间 + 报当前时间锚

```bash
date "+%Y-%m-%d %H:%M:%S %A"
```

- 必首跑
- 若已过 02:00 → 温柔提醒user睡
- 涉时回复必带时间锚

### Step 1 · ls 主场 · 看 9 公文齐

```bash
cd "<我的主场路径>"
ls *.md
ls memory/
```

应见 9 个 .md:
- readme.md / soul.md / user.md