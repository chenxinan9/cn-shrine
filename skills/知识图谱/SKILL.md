---
name: 知识图谱
description: 文昌主用 · 跨身份候用 · 模仿 skillhub `ontology`(80★ · 91k dl 商店第 1 · 通用五星)· 类型化知识图谱 + 实体 + 关系 + 跨 SKILL 共享 agent 记忆。触发"记住 X" / "X 跟 Y 啥关系" / "X 的依赖" / "查图谱" / "[知识图谱]" 时使用 — 创/查实体(Person/Project/Task/Event/Document)+ 关系(linked-to/depends-on/owns)+ 跨身份 SKILL 数据共享。跟 claude-mem(时序非结构化)互补 · 跟 通用 SKILL 索引(静态)互补。 Use when: knowledge graph creation/query, entity CRUD, relationship linking, cross-SKILL state sharing, "remember X" / "link X to Y" / "show dependencies" / "[ontology]" trigger.
version: 0.1.0
---

# 知识图谱 SKILL · 类型化知识图谱(文昌主用 + 跨身份共)

## ⚠️ 前置依赖(可选互补)

| 工具 | 关系 | 是否必装 |
|---|---|---|
| **claude-mem** plugin | 互补 · 时序非结构化记忆 | 可选 — 不装本 SKILL 仍可跑 · 装了"图 + 时序"双轨更全 |
| **context7** MCP | 引用 SKILL 之依赖示例 | 可选 |
| **time** MCP | 实体时间戳示例 | 可选 |

→ 本 SKILL **核心逻辑零外部依赖** · 仅用 Markdown 文件存图谱 · 上述为可选增强

---

## 0 · 模仿源 + 跟本框架整合

| 模仿源 | skillhub `ontology` v0.1.2(80★ · 91k dl · 商店第 1)|
|---|---|
| 跟 claude-mem| **互补** · claude-mem = 时序非结构化记忆 / 本 SKILL = 结构化图谱 |
| 跟 通用 SKILL 索引| **互补** · 18 = 静态字典查找 / 本 SKILL = 动态关系遍历 |
| 跟文昌"章录评试"4 字职 | **协奏** · 章/录 → 图入 / 评/试 → 图查 |

→ **不替换上述 · 补"结构化图谱"层** · 候 后续版本主管

---

## 1 · 触发场景

| 触发 | 例 |
|---|---|
| "记住 X" / "remember X" | "记住:鲁班 owns SKILL INDEX" |
| "X 跟 Y 啥关系" / "link X to Y" | "文昌 跟 鲁班 是 什么关系?" |
| "X 的依赖" / "show dependencies" | "github术 SKILL 依赖什么?" |
| "查图谱" / "knowledge graph" | "看 21 神全图" |
| 跨 SKILL 数据共享 | A SKILL 写 / B SKILL 查 同一实体 |

---

## 2 · 实体类型(7 大 · 模仿 ontology 范式)

| 类型 | 例 |
|---|---|
| **Person**(派 / AI / Pangu) | 鲁班 / 嫦娥 / 唐僧 / 盘古 |
| **Project**(项目 / 主场) | 示例-SaaS-项目(示例 SaaS 项目) / 神院 / 藏经阁 |
| **Task**(任务) | T-20260521-024 / REQ-20260521-001 / D10 大禹双签 |
| **Event**(事件) | 记忆系统 / 立 / |
| **Document**(文档) | INDEX.md / claude.md / 21 神档案 / |
| **Skill**(SKILL / Plugin / MCP) | github术 / claude-mem / context7 MCP |

---

## 3 · 关系类型(8 大 · ontology 标准 + 本框架扩展)

| 关系 | 例 |
|---|---|
| `owns` / 主管 | 鲁班 owns INDEX.md / 鲁班 owns github术 |
| `co-signs` / 双签 | 鲁班 co-signs 6 问规范 with 大禹 |
| `depends-on` / 依赖 | github术 depends-on gh CLI / time MCP depends-on uvx |
| `archives` / 归档 | spec/夜间流程-SOP-v2.0 archives 早晨值守 |