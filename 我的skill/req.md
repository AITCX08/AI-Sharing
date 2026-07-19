---
name: req
description: Clarify vague or high-impact software requests into an executable requirement with scope, assumptions, and testable acceptance criteria. Use when the user writes /req, req:, "需求澄清", "梳理需求", or describes an unclear feature, bug, UI change, performance issue, migration, permission, payment, or deployment change.
---

# Requirement Clarifier

把口语化需求整理成开发人员或 AI 不必猜测就能执行的任务。

## 工作流

1. 用简洁中文复述目标。
2. 先检查已有代码、配置和上下文；不要问可以自行查到的信息。
3. 只问“答案会改变实现、风险或验收结果”的问题。最多三个；需要时一次只问一个。
4. 明确说明低风险假设。用户已经要求实施时，除非存在高风险的未决问题，否则带着假设继续推进。
5. 支付、权限、用户数据、删除、数据库迁移、生产部署等不可逆操作，必须在执行前说明风险并请求确认。

## 输出格式

```markdown
## 需求：<一句话标题>

**类型**：新功能 / Bug 修复 / UI 调整 / 性能优化 / 配置或部署
**位置**：<页面、模块、API 或服务>
**目标用户与触发条件**：<谁在什么情况下做什么>
**期望结果**：
- <可观察结果>

**范围外**：
- <明确不改什么>

**验收标准**：
- [ ] <可测试条件>

**涉及层级**：前端 / 后端 / 数据库 / 配置 / 部署
**风险、假设或待确认项**：<仅在存在时写>
```

## 按任务类型补充

- **Bug**：写清现象、期望行为和复现条件。
- **新功能或 UI**：写清用户动作、影响的数据、可见性或权限规则，以及不变的部分。
- **性能**：写清当前基线、目标、数据量/负载和测量方法。
- **配置或部署**：写清目标环境、服务影响和回滚路径。

## 边界

- 不伪造确定性：区分已确认事实、假设和未决问题。
- 术语第一次出现时，必要时用一句大白话解释。
- 明确且低风险的小任务不应强行进入需求访谈。
