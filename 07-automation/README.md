# WorkBuddy Automation 实践指南

## TL;DR

Automation 适合周期性、重复性、低歧义的办公任务，例如日报、周报、资讯简报、定时数据整理。自动化会在无人值守时以当前登录身份发起 Agent 任务，所以不能只看 prompt 是否写得顺，还要检查工作目录、调度频率、模型、Skill、连接器、外发渠道和失败处理。

## Official facts

- WorkBuddy 官方文档说明，自动化可按设定时间自动执行周期性、重复性任务，并将结果保存到指定目录。
- 官方说明自动化配置保存在本地客户端，包括任务名称、prompt、调度规则、工作目录、执行状态等。
- 自动化会在指定时间以当前登录身份自动发起 Agent 任务，并按 prompt 执行查询、汇总、文件处理等工作。
- 创建自动化时可配置名称、工作空间、提示词、模型和技能、定时规则、生效日期区间，以及是否推送到 WorkBuddy 小程序。
- 官方说明工作空间用于指定任务执行目录及文件保存位置，默认可自动分配 automation-xxxx 工作空间。
- 自动化调用 MCP、连接器、OAuth 服务时会使用已授权凭据；自动化本身不另存凭据。
- 官方提醒任务在无人值守下自动执行，应审慎设置涉及文件写入、删除、资金操作的 prompt。

## Practical interpretation

Automation 的关键是“可重复”和“可检查”。一个好自动化不是把一句话定时运行，而是把输入源、执行步骤、输出位置、异常处理和验收标准都固定下来。它最适合信息汇总、固定格式报告、低风险提醒和稳定数据源的周期任务。

不要把 Automation 用作高风险无人审批流程。只要任务会写文件、删文件、对外发送、调用连接器或使用第三方凭据，就应该先跑手动流程，确认稳定后再低频试运行。

## How to use

1. 先手动执行一次任务，确认 prompt 和输出格式可用。
2. 为自动化单独建立工作空间，避免污染其他任务文件。
3. 写清任务目标、数据源范围、输出路径、格式要求和禁止操作。
4. 选择必要模型和 Skill，不启用无关工具。
5. 从低频调度开始，例如每天一次或每周一次。
6. 开启推送前确认结果内容是否适合同步到小程序。
7. 建立执行记录检查机制，定期复盘失败、重复、偏差和成本。

## Best practices

- 自动化 prompt 应包含“只读取这些来源”和“不要修改这些文件”。
- 文件输出使用日期或批次命名，避免覆盖历史结果。
- 对外发送类自动化先输出草稿，不直接发送。
- 对连接器任务限定时间范围、项目范围、标签或收件人。
- 对长期自动化设置结束日期或定期复核日期。
- 对异常结果建立人工检查入口，例如“如信息不足，输出无法完成原因，不要编造”。
- 对积分和第三方费用做预算提醒。

## Common mistakes

- 把尚未手动验证的 prompt 直接设成自动化。
- 自动化使用宽泛指令，例如“每天整理所有重要信息”。
- 输出文件没有固定目录和命名规则，导致覆盖或散落。
- 长期无人检查执行结果。
- 自动化调用连接器时没有限定读取范围。
- 让无人值守任务直接删除文件、发送外部消息或进行资金类操作。

## Security / permission notes

自动化的风险来自“无人值守 + 当前身份 + 已授权工具”。它可能触发模型、Skill、MCP、连接器、OAuth 服务、通知渠道和本地文件读写。

企业场景建议默认禁止以下无人值守操作：

- 删除或批量覆盖文件。
- 对外发送邮件、消息、公告或客户通知。
- 修改知识库、合同、财务、客户或人事数据。
- 使用资金、支付、采购、订单类服务。
- 在未审计的 Skill 或自定义连接器上运行。

如必须启用，应增加审批、日志、回滚、通知和定期复核。

## Template or checklist

```markdown
## Automation Design Example

- 自动化名称：
- 业务目标：
- 执行频率：
- 生效日期：
- 工作空间：
- 输入来源：
- 使用模型 / Skill / Connector：
- 输出路径：
- 是否推送到小程序：
- 禁止操作：
- 首次试运行结果：
- 失败处理：
- 复核人：
```

## Further Reading

- [WorkBuddy 官方文档：自动化](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [WorkBuddy 官方文档：连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 官方文档：技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [Automation Design Template](../templates/automation-template.md)
- [WorkBuddy Security Checklist](../templates/security-checklist.md)
- [sources.md](../sources.md)
