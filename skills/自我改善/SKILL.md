---
name: 自我改善
version: 0.1.0
---

# 自我改善 SKILL · 跨身份持续改善聚合

## 0 · 模仿源 + 跟本框架整合

| 模仿源 | skillhub `self-improving-agent` v3.0.21(80★ · 81k dl · 通用五星 · Top 5)|
|---|---|
| 跟本框架 闭环铁律 | 协奏(列问 → 自跑 → 自执行 → 自沉淀)|
| 跟本框架反 AI 通病自检 SKILL | 协奏(pattern 类)|

→ **本 SKILL 不替换上述 · 是聚合入口 · 派内 AI 用 1 SKILL 调全 4 套**

---

## 1 · 触发场景(6 + 1 = 7)

| # | 场景 | 归档到 |
|---|---|---|
| 2 | 用户纠正 "No, that's wrong" / "Actually..." | **启发本**(派 memory/启发本/I-XX-{NN}.md)|
| 3 | 请求不存在的能力 | **特征请求**(派 memory/.drafts/FEATURE_REQUESTS-{month}.md)|
| 4 | 外部 API / 工具失败 | **错误本** |
| 5 | 知识过时 / 不正确 | **启发本** |
| 6 | 发现更好方法 / 复用模式 | **启发本** + 候升 SKILL |
| 7 · 大任务前 | **Review** 派 memory/启发本 + 错误本(防重犯)|

---

## 2 · `.learnings/` 三件套范式(借鉴 skillhub 简化版)

派内 `memory/.learnings/` 初始化:

```bash
mkdir -p memory/.learnings
[ -f memory/.learnings/LEARNINGS.md ] || cat > memory/.learnings/LEARNINGS.md <<EOF
# Learnings (派内启示快记 · I-XX-候)

| 日 | 类 | 内容 | 触发 | 候升 |
|---|---|---|---|---|
EOF

[ -f memory/.learnings/ERRORS.md ] || cat > memory/.learnings/ERRORS.md <<EOF
# Errors (派内错误快记 · 候大禹错误本)

| 日 | 命令/动作 | 错 | 防 |
|---|---|---|---|
EOF
