# WorkBuddy Connector 实践指南

## TL;DR

Connector 用来把 WorkBuddy 接到外部服务，让 Agent 能按授权范围查询、读取、创建、编辑或发送第三方系统中的内容。连接器的核心不是“多一个入口”，而是“以你的身份调用外部服务”。启用前必须确认授权范围、凭据管理、数据流向和撤销方式。

## Official facts

- WorkBuddy 官方文档说明，连接器用于将 WorkBuddy 与外部服务对接，实现数据互通与能力扩展。
- 官方将连接器描述为 WorkBuddy 与外部服务之间的桥梁，可将外部能力引入 AI 工作流。
- 官方说明连接器技术形态包括 MCP + CLI 和 Skill + CLI，二者在数据收集和权限边界上遵循一致原则。
- 官方列出当前已支持 QQ 邮箱、腾讯文档、腾讯乐享、腾讯会议、TAPD 等连接器，并支持自定义连接器。
- 官方示例中，QQ 邮箱连接器支持收发、搜索和整理 QQ 邮件；腾讯乐享连接器支持搜索、创建和管理知识库文档。
- 官方说明每个连接器独立授权，不主动定时抓取，不超出用户已有权限范围。
- 连接器自身读写不消耗积分；WorkBuddy 对外部数据进行理解、汇总时会消耗积分。

## Practical interpretation

连接器适合把“请帮我查一下外部系统”变成可执行任务，例如汇总邮件、检索知识库、整理会议、查询项目数据。它也会扩大影响范围：错误的 prompt 可能导致错误邮件、错误文档修改或错误消息发送。

连接器不是 WorkBuddy 官方对所有第三方服务的统一安全背书。官方支持的连接器仍要按企业授权和数据分类使用；自定义连接器更要由配置者负责访问范围、凭据、接口行为和日志审计。

## How to use

1. 确认任务确实需要访问外部服务，而不是可以通过上传材料完成。
2. 在连接器管理页面添加目标连接器，按官方流程授权。
3. 授权时逐项确认读取、写入、发送、删除等权限。
4. 在任务 prompt 中限定数据范围，例如时间、项目、文件夹、标签、收件人。
5. 对写入、发送、删除类操作要求先生成草稿或操作清单。
6. 完成阶段性任务后，关闭或断开不再需要的连接器。
7. 定期检查授权状态和第三方服务中的应用授权记录。

## Best practices

- 连接器按“最小可用范围”授权；能只读就不要写入，能单项目就不要全局。
- 对邮件、会议、文档、项目管理系统分别建立使用边界。
- 自定义连接器上线前做接口清单、凭据清单、失败场景和审计日志检查。
- 外发内容必须先预览，特别是邮件、即时消息、客户通知和跨部门公告。
- 对知识库写入类任务保留版本记录和人工审核。
- 对 API Key、Token、OAuth 凭据建立撤销和轮换流程。

## Common mistakes

- 授权时只看“连接成功”，不看具体权限。
- 让 WorkBuddy 在没有范围限制的情况下搜索整个邮箱或知识库。
- 把连接器结果当成绝对正确，忽略第三方数据本身可能过期或不完整。
- 长期保留不再使用的连接器授权。
- 在公共设备或共享环境填写 API Key。
- 自定义连接器没有审计访问范围和错误处理。

## Security / permission notes

连接器会涉及第三方账号标识、授权凭据、第三方业务数据，以及在明确指令下写入的数据。凭据由 WorkBuddy 维护以便代用户调用外部服务；调用行为通常以用户本人身份和已有权限执行。

高风险连接器任务包括：

- 代发邮件、会议邀请或即时消息。
- 创建、编辑、删除外部文档。
- 访问客户、合同、财务、项目缺陷或内部知识库。
- 自定义 MCP 连接器接入企业内部系统。
- 使用 API Key 或 Token 调用第三方服务。

## Template or checklist

```markdown
## Connector Evaluation Example

- Connector 名称：
- 外部服务：
- 授权账号：
- 读取范围：
- 写入 / 发送范围：
- 凭据类型：OAuth / API Key / Token / 其他
- 是否支持撤销授权：
- 允许任务：
- 禁止任务：
- 审计方式：
- 负责人：
```

## Further Reading

- [WorkBuddy 官方文档：连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 官方文档：技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy 官方文档：数据管理](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data)
- [WorkBuddy Security Checklist](../templates/security-checklist.md)
- [sources.md](../sources.md)
