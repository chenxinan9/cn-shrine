---
name: 结合
description: 让 AI 吃我的项目历史,不要给通用回答。触发 "[结合]" 时,AI 主动加载项目历史 / 工具栈 / 红线 / 保密项,再回答。 Use when: load project history, avoid generic answers, cross-discipline call.
---

# 结合 Skill

## 触发关键词
- `[结合]`
- `结合我项目`
- `不要通用回答`

## 执行流程

收到触发后,严格结合以下历史:

1. 项目:示例 SaaS 项目(your-project v67-v68)+ legacy-framework
2. 已踩坑:OpenHands / Dify / Coze / Hermes SaaS / 示例代养
3. 已选工具栈:Claude Code 主 / Codex 备 / your-local-llm 5 模型 / your-llm API / your-api-gw 网关
4. 5 红线
5. 13 项目矩阵(对外保密)

回答前先告诉Pangu"你结合了上面哪几条"

输出结构:
- 项目历史里的相关事实
- 这件事跟哪些决策呼应 / 冲突
- 基于历史的具体建议(可执行)
- 我可能没看到的风险

末尾标"专家级水平 X/10"

## Gotchas

1. **不要给"通用回答"** — 触发"结合"就必须吃完上面 5 条历史再答,不能用"AI 一般会建议..."这种泛话
2. **不要漏 13 项目矩阵保密** — 对外内容必须脱敏(2026-05-16 / open-source-analysis 边界)
3. **不要假设Pangu"什么都记得"** — Pangu 25 AI 协作,需要 AI 重新对齐历史,**不能让Pangu自己讲"我之前怎么决定的"**
4. **不要在多 AI 调度时让任一 AI 独大** — 调度your-llm(发散)/Codex(执行)/your-llm(对赌)等要"任人唯贤",不"宫斗"
5. **不要因为"我已经结合了"就停止 grep** — 每次"结合"都要重新 grep 全 Mac,因为 5 本随时在更新

## 关联资源
- 详细模板见 `~/Desktop/提示词模版/结合.md`
- 错误本对偶: 根因 G(没追问推进)
- 启发本对偶: (避免造并行轮子)

## Gotchas(通用避雷 · 2026-05-21 v0.8 鲁班批补 · 候 vessel 实战补本派真痛点)

### Gotcha 1 · 不要堆万字 / 假装做(反 ~ 9 通病 #1, #4)
- **症状**:输出 5000+ 字 / 无真物落档 / 无路径 / 无数据
- **后果**:噪音 + 浪费 context · Pangu"看了头大"
- **正确**:真物 ≥ 3 + 路径 + ≤ 200 字总结 · grep "完美/必然/一定" = 0

### Gotcha 2 · 不要凭"我觉得"触发 / 过早抽象(反过早抽象 · 反闭门 )