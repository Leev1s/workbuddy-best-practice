# Workplace Agent Workflows

## TL;DR

Workflow 是可复用的办公任务流程，不是一次性 prompt。一个可靠的 WorkBuddy workflow 通常经过：准备工作空间、写 Task Brief、补充上下文、先跑小样本、检查结果区、沉淀模板、再考虑 Expert / Skill / Connector / Automation。

## Official facts

WorkBuddy 官方文档说明，创建任务时可以选择工作目录并补充上下文；任务执行后可通过结果区查看产物、全部文件、变更和预览。官方还提供专家、Skill、Connector、Automation、权限模式、记忆、模型配置和 Cloud Agent 等能力说明。

## Practical interpretation

WorkBuddy 的强项是把自然语言任务转成多步骤执行。最佳实践不是把所有任务都自动化，而是先把流程跑通、验收稳定，再决定是否升级为能力资产：

1. 手动任务：适合首次尝试。
2. 可复用 Task Brief：适合重复但仍需人工判断的任务。
3. Expert / Expert Team：适合领域视角明确或多角色协作的任务。
4. Skill / Connector：适合需要工具能力或外部系统数据的任务。
5. Automation：适合触发条件稳定、风险可控、验收标准明确的任务。
6. Cloud Agent：适合企业级 Agent 运行、接入、版本和评测管理。

## How to use

### Workflow 1: 从聊天到可验收任务

1. 写明目标和交付物。
2. 指定工作目录。
3. 上传或引用输入材料。
4. 要求先列计划。
5. 执行后查看产物、全部文件、变更和预览。
6. 把成功 prompt 保存为模板。

### Workflow 2: 从人工流程到自动化

1. 连续手动跑 2-3 次，记录输入、输出和失败点。
2. 提取固定步骤、变量和人工判断节点。
3. 写 Automation 草案，明确触发条件和停止条件。
4. 在低风险样本上测试。
5. 增加通知、日志、人工确认和回滚方案。

### Workflow 3: 从个人经验到 Expert

1. 描述角色、人设、方法论和任务边界。
2. 准备典型任务样例。
3. 用小任务验证输出质量。
4. 对高风险领域加免责声明和人工复核要求。
5. 再评估是否需要配套 Skill、Connector 或专家团。

## Best practices

- 先用默认权限和独立工作空间跑通，再放大范围。
- 不把第一次成功直接升级为自动化。
- 所有 workflow 都保留验收标准和失败处理。
- 对外部数据和第三方服务使用来源白名单。
- 对周期性任务定期复查 Changelog 和产品界面，防止版本变化影响流程。

## Common mistakes

- 把“能执行”误认为“适合自动化”。
- 没有先验收变更视图，就接受文件修改。
- 把 Skill 当成安全工具，忽略脚本、文件和第三方外发风险。
- 把 Memory 当成项目知识库，未核验就依赖旧偏好或历史信息。

## Security / permission notes

Workflow 必须包含权限边界：工作空间、可读写路径、是否允许外部服务、是否允许脚本、是否允许删除或覆盖文件。涉及 Full Access、第三方 Skill、Connector、Automation 或 Cloud Agent 凭据时，应增加人工审批。

## Template or checklist

- [Review Checklist](../templates/review-checklist.md)
- [Automation Template](../templates/automation-template.md)
- [Security Checklist](../templates/security-checklist.md)

## Further Reading

- [WorkBuddy Create Task](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy Results](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy Expert Center](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center)
- [WorkBuddy Skills Market](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy Connector](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy Automation Guide](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
