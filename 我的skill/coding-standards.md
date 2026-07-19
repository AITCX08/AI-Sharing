---
name: coding-standards
description: Apply safe, maintainable, and verifiable engineering standards when implementing or reviewing code, configuration, database, API, or deployment changes. Use for feature work, bug fixes, refactors, migrations, security-sensitive changes, and before declaring a development task complete.
---

# Coding Standards

适用于所有语言和项目的开发底线：改动聚焦、数据安全、行为可验证、结果可追溯。

## 开始前

- 阅读相关代码、配置和现有行为，确认目标、边界与验收标准。
- 保持最小改动：不顺手重构无关代码，不覆盖既有修改，不无故升级依赖。
- 识别高风险区域：密钥、权限、支付、用户数据、数据库迁移、删除和生产部署；不可逆操作前先说明影响。

## 实现规则

- 使用能表达业务含义的命名，保持函数和组件职责单一。
- 优先复用项目已有模式；不要为了“看起来高级”重复代码或引入新框架。
- 校验外部输入，并在服务端做权限判断。
- 密钥不得进入代码、提交、截图或日志；使用环境变量或项目的密钥管理方式。
- 远程调用设置超时并处理失败；关联写入使用事务；订单、余额、额度、库存等重复请求必须幂等。
- 不吞异常，不在操作失败时伪造成功。

## 验证与交付

- 覆盖主流程、预期失败路径和相关边界条件。
- 配置或部署改动还要验证启动、健康检查、关键接口、日志和必要连接。
- 检查最终 diff，重点排查密钥、无关文件、破坏性变更和遗漏的迁移。
- 汇报修改文件、验证命令与结果、剩余风险；没有新验证证据就不宣称完成。
