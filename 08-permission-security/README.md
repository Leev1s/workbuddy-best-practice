# WorkBuddy 权限、安全与企业治理

## TL;DR

企业使用 WorkBuddy 时，安全治理的核心不是“禁止 Agent 做事”，而是把每次任务限制在明确的工作空间、明确的数据范围、明确的权限模式和明确的验收流程内。默认权限应作为日常基线；Full Access、第三方 Skill、Connector、Automation、Memory 和文件分享都应进入更严格的审批、记录和复核。

## Official facts

- WorkBuddy 官方权限模式文档说明，WorkBuddy 提供默认权限和 Full Access / 完全访问权限。默认权限下，WorkBuddy 可在指定工作空间内执行常规任务，遇到工作空间外写入、删除文件、执行脚本或调用敏感能力等高风险动作时会要求确认。
- 官方文档将工作空间描述为当前任务主要读取和保存文件的文件夹，并建议重要资料先放入独立文件夹、使用副本、保留备份。
- 官方 Skill 文档说明，Skill 会封装脚本与工作流，用于扩展工具能力；非官方 Skill 可能存在恶意提示词注入、越权访问、后门程序等隐患，建议优先使用官方推荐 Skill。
- 官方 Connector 文档说明，连接器用于接入外部服务，支持 MCP + CLI、Skill + CLI 等形态；连接器按用户已有权限访问第三方服务，可启用、禁用或断开；自定义连接器的访问范围由配置决定。
- 官方 Automation 文档说明，自动化在本地客户端保存任务名称、prompt、调度规则、工作目录、执行状态等配置，并在指定时间以当前登录身份自动发起 Agent 任务。
- 官方 Memory 文档说明，记忆会从会话历史中抽取事实、偏好、人物关系、跟进事项等记忆数据，可在设置中查看、编辑、删除或关闭；依赖记忆做重要判断前建议核验。
- 官方数据管理文档说明，数据管理入口可管理已分享文件和已归档任务；取消分享后，他人无法再通过链接访问。

## Practical interpretation

WorkBuddy 的企业风险主要来自五类边界：

- 文件边界：读写、覆盖、删除、移动是否只发生在本次工作空间内。
- 身份边界：Connector、Automation、第三方服务调用是否以员工本人身份执行。
- 数据边界：输入、输出、Memory、分享链接、日志是否包含客户资料、个人信息、合同、财务或凭证。
- 工具边界：Skill、Connector、脚本、CLI、MCP 是否可信、可审计、可禁用、可撤销。
- 时间边界：Automation 和 Cloud Agent 类任务是否会在无人值守时持续执行。

因此，企业规范应把 WorkBuddy 任务从“对话”改造成“可审批、可验收、可追溯、可回滚”的工作单元。

## How to use

1. 为任务创建独立工作空间，只放入必要文件和副本。
2. 在 task brief 中写明数据分类、允许读取路径、允许写入路径、禁止操作和验收标准。
3. 默认使用默认权限；遇到 Full Access，要求记录业务理由、隔离方式、备份位置、审批人和关闭时间。
4. 启用 Skill 前完成来源、权限、脚本、数据流和第三方共享评估。
5. 启用 Connector 前确认账号归属、授权范围、外部服务协议、写操作风险和撤销方式。
6. 创建 Automation 前先手动运行并验收；无人值守任务必须有低频试运行、日志、通知、停止开关和人工审批门。
7. 使用 Memory 时避免把敏感私人信息、客户数据、账号、token、内部策略写入会话；重要判断前核验记忆内容。
8. 分享结果文件前检查内容、链接范围、接收人和撤销计划。

## Best practices

- 把默认权限写入团队基线：日常任务默认不使用 Full Access。
- 把 Full Access 写成例外流程：只允许在隔离、可恢复、可信任务中短时间开启。
- 对批量文件操作采用“三步法”：先列清单，再小样本试跑，最后执行。
- 对所有对外发送动作采用“双确认”：确认收件人 / 目标系统，再确认正文 / 文件内容。
- 对 Skill 和 Connector 采用最小启用原则：只启用当前任务需要的能力，用完关闭或断开。
- 对 Automation 采用“低频试运行优先”：先人工验收结果，再扩大调度频率。
- 对 Memory 采用“少写敏感、定期清理、重要核验”：不要把它当合规记录或企业知识库。
- 对 `.workbuddy/` 采用只读优先：它是本仓库实践约定，不是 WorkBuddy 官方规范，也不等同于官方 Memory。

## Common mistakes

- 为了减少弹窗长期启用 Full Access。
- 在桌面、下载目录、个人文档根目录或生产项目根目录直接运行批处理。
- 安装第三方 Skill 后不检查脚本、权限和外部数据流。
- Connector 使用个人账号连接企业系统，却没有记录账号责任人和撤销方式。
- Automation prompt 写得模糊，导致无人值守任务误删、误改或误发。
- 把 Memory 中自动抽取的信息当成事实来源，未复核就用于审批、财务、法务或人事判断。
- 分享产物后忘记取消链接，或未检查文件中是否包含敏感信息。

## Security / permission notes

### 权限模式

默认权限是日常基线。Full Access 应被视为高风险例外：它减少确认，但也减少拦截误操作的机会。企业内部应要求 Full Access 任务具备隔离工作空间、备份、审批、可回滚和关闭时间。

### Skill

Skill 可能读写文件、执行脚本、调用第三方 API 或控制输入输出。官方文档明确提醒非官方 Skill 风险，因此任何非官方 Skill 都应先通过安全评估；不能因为它“能完成任务”就默认可信。

### Connector

Connector 的风险不是抽象的“连接外部服务”，而是以授权账号执行真实读写、消息发送、会议、文档、项目管理等操作。涉及企业系统时，应记录账号、授权范围、外部服务、撤销方式和对外写入审批。

### Automation

Automation 会按调度规则以当前登录身份触发任务。所有无人值守任务都应避免直接删除、覆盖、资金操作或未经审核的对外发送；确需执行时，应设置人工审批门和快速禁用方案。

### Memory

Memory 可提升连续性，但它不是审计系统，也不应承载敏感资料。记忆由模型抽取，可能存在概括偏差或时效性问题；重要决策前必须核验原始材料。

### Data sharing

已分享文件应定期清理。对外分享前要检查内容、接收范围和保密标记；不再需要公开访问时，及时取消分享。

## Template or checklist

- [WorkBuddy Security Checklist](../templates/security-checklist.md)
- [Skill Evaluation Template](../templates/skill-evaluation-template.md)
- [Connector Evaluation Template](../templates/connector-evaluation-template.md)
- [Automation Design Template](../templates/automation-template.md)
- [Permission Modes](permission-modes.md)

## Further Reading

- [WorkBuddy 两个权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy 技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy 连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 自动化](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [WorkBuddy 记忆](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory)
- [WorkBuddy 数据管理](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data-Management)
