---
name: 5问造技能
description: 元 SKILL — 用 5 个必问 + 3 个补充访谈,把user想要的能力封装成新 SKILL.md。基于一舟 skill-creator 简化版。触发 "[5问造技能]" 或user说"建一个 X 触发词包"时使用。 Use when: creating new SKILL via interview, meta-SKILL crafting, build trigger package, capability packaging.
---

# 5问造技能 Skill(元 SKILL)

## 触发关键词
- `[5问造技能]`
- `建一个 X 触发词包`
- `造 SKILL`
- `想让 Claude 记住 X`

## 核心定位

**元 SKILL** = 用来造其他 SKILL 的 SKILL。
user想要新能力 = 我用 5 问访谈 + 自动产 SKILL.md → 全流程 < 10 分钟。

## 工作流

### Step 1 · 5 必问(逐个,等回答再下一题)

```
Q1: 这个能力解决什么问题?(用 1-2 句话)

Q2: 什么情况下会触发这个能力?(给我 2-3 个具体例子)

Q3: 这个能力的输出是什么?(展示一个理想输出例子)

Q4: 需要哪些外部工具 / 服务?(浏览器 / API / Bash / 本地文件 / ...)

Q5: 这个能力最容易在哪里出错?(你之前手动做时遇到过什么坑?)
 → 这答案直接进 Gotchas
```

### Step 2 · 验证非内置能力(防止"造无用 SKILL")

判断user描述的能力是不是 Claude 内置:

| 内置(不需要 SKILL) | 需要 SKILL |
|---|---|
| 翻译 / 摘要 / 改写 / 润色 | 访问特定外部服务(认证 API)|
| 写代码 / debug / 解释代码 | 多步命令行组合 |
| 数学计算 | 强制标准化输出模板 |
| 格式转换(JSON/MD/CSV) | 平台特有格式 |
| 知识问答 | 多工具组合工作流 |

如是内置 → 告知user"直接说 `{具体指令}` 即可,不需要 SKILL"

### Step 3 · 设计 SKILL 元素

#### name 命名规则
- **全中文优先**(user英语忘光, 启发)
- 动词开头(`参谋一刀` ✅ / `深度` 也行,反映动作)