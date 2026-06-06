# From Manual Run to Automation

## TL;DR

Automation 只适合已经被人工跑通、输入稳定、风险可控、验收清楚的流程。不要把模糊需求直接交给无人值守自动化。

## Official facts

WorkBuddy 官方文档把 Automation 作为功能模块之一；权限模式文档提醒，高风险操作包括工作空间外写入、删除文件、执行脚本或调用敏感能力，默认权限会在关键节点要求确认，而 Full Access 会关闭这些二次确认。

## Practical interpretation

自动化的前提不是“任务可以描述”，而是“任务可以重复”。企业场景中，自动化要同时回答四个问题：

- 什么时候触发？
- 输入从哪里来？
- 什么情况下停止？
- 谁负责验收和处理异常？

## How to use

### Step 1: 手动跑通

先用 Task Brief 手动执行，至少记录：

- 输入材料类型和位置。
- 输出文件命名和格式。
- 中间是否需要人工判断。
- 哪些操作会修改、删除、覆盖或外发数据。
- 结果区如何验收。

### Step 2: 小样本验证

选择低风险样本，要求 WorkBuddy：

```markdown
请先只处理 3 个样本文件。
执行前列出计划、目标路径和可能修改的文件。
不要删除原文件；把结果写入 output/。
完成后输出验收清单。
```

### Step 3: 写自动化草案

```markdown
自动化名称：

触发方式：
- [一次性 / 每天 / 每周 / 外部事件]

输入来源：
- [文件夹 / Connector / 资料库 / 人工上传]

执行步骤：
1. 
2. 
3. 

停止条件：
- 缺少输入
- 权限失败
- 输出异常
- 需要删除、覆盖、外发或执行未知脚本

人工确认：
- [哪些步骤必须确认]

验收标准：
- 
```

### Step 4: 上线后复查

每次 WorkBuddy Changelog 涉及 Automation、权限、Skill、Connector、模型或结果查看时，复查相关自动化是否需要更新。

## Best practices

- 自动化产物写入独立输出目录。
- 首次上线只处理低风险数据。
- 对失败情况保留人工处理流程。
- 对周期性任务设置复查节奏。
- 不在自动化里隐藏凭据、账号或内部系统 token。

## Common mistakes

- 还没有稳定验收标准就设置定时任务。
- 自动化默认处理工作空间外目录。
- 缺少异常停止条件，导致错误结果被持续推送。
- 让自动化直接删除或覆盖唯一副本。

## Security / permission notes

无人值守流程放大风险。涉及第三方服务、外部 API、文件删除、批量写入、脚本执行或 Full Access 时，应先通过安全评估模板，并保留人工审批、备份和回滚方案。

## Further Reading

- [WorkBuddy Automation Guide](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [WorkBuddy Permission Modes](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [Automation Template](../templates/automation-template.md)
- [Security Checklist](../templates/security-checklist.md)
