# WorkBuddy 权限模式与企业安全规范

## TL;DR

默认权限适合日常任务，因为它在工作空间内保持效率，并在高风险操作前要求确认。完全访问权限 / Full Access 只适合可信、隔离、可恢复的环境，不适合直接用于生产资料、客户资料、财务资料或唯一副本。企业场景应默认采用最小权限、独立工作空间、先清单后执行、人工审批和可回滚策略。

## Official facts

- 官方权限模式页面说明，WorkBuddy 提供默认权限和完全访问权限两种模式。
- 官方说明建议日常使用默认权限；在默认权限下，AI 可以在指定工作空间中完成常规任务，遇到高风险操作时会请求用户确认。
- 官方说明将工作空间定义为当前任务主要读取和保存文件的文件夹。
- 官方列出的常见确认场景包括写入或修改工作空间外文件、删除文件或目录、执行脚本 / 命令 / 外部程序、调用敏感能力。
- 官方说明 Full Access / 完全放开会关闭上述二次确认，应只在可信任务、隔离环境或临时测试目录中谨慎使用。

## Practical interpretation

权限模式不是效率开关，而是风险边界。默认权限让 WorkBuddy 在多数低风险步骤上保持自动执行，同时把高风险步骤交还给人类确认。Full Access 减少确认成本，但也放大了误解任务、路径写错、脚本行为异常或第三方工具不可信的影响。

企业使用时，应把权限模式纳入安全规范：

- 默认权限 = 日常基线。
- Full Access = 例外，需要隔离、备份、审批和结束后关闭。
- 工作空间 = 每个任务的风险容器。

## How to use

1. 为每个任务建立独立工作空间。
2. 如果工作空间包含项目级上下文文档，默认只读取稳定内容；如需修改，先列出变更计划和回滚方式。
3. 把需要处理的文件副本放入工作空间。
4. 默认使用默认权限。
5. 涉及删除、覆盖、批量重命名、脚本、命令、外部程序或敏感能力时，要求先解释和列清单。
6. 如必须使用 Full Access，确认环境隔离、文件可恢复、任务可信，并在完成后立即关闭。
7. 企业场景中记录权限决策、审批人、任务范围和回滚方案。

## High-risk operations

- 工作空间外写入或修改文件。
- 删除文件或目录。
- 批量移动、重命名、覆盖文件。
- 执行脚本、命令或外部程序。
- 调用敏感能力、系统级 API 或外部服务。
- 处理客户资料、财务资料、合同、个人信息、密钥、凭证。
- 无人值守 Automation 中执行上述任何操作。

## Best practices

- 每个任务单独工作空间。
- 重要文件使用副本，不直接处理唯一原件。
- 批量删除前先生成清单，不直接删除。
- 脚本先解释、再小样本测试、最后执行。
- Full Access 用完即关。
- Full Access 下尤其要防止 Agent 误改项目规则、权限记录、维护记录或安全清单。
- 对第三方 Skill / Connector 先做安全评估。
- 企业场景不建议直接 Full Access；如必须使用，应在隔离目录、虚拟机、Docker 或临时测试环境中进行。

## Common mistakes

- 为了少点确认长期启用 Full Access。
- 在桌面、下载目录、个人文档根目录或项目根目录直接运行批量任务。
- 没有备份就处理财务、合同、客户资料。
- 不看确认弹窗的路径和影响范围。
- 让 Agent 执行不理解的脚本。
- 将 Automation 设为无人值守，却没有失败通知和回滚方案。

## Security / permission notes

### 默认权限适合日常任务

日常文档生成、表格处理、资料整理、报告草稿和小规模文件处理，优先使用默认权限。默认权限的价值是“关键风险点停下来”。

### Full Access 只适合可信、隔离、可恢复环境

Full Access 不等于更安全，也不代表 WorkBuddy 自动替用户承担风险。它适合短时间、明确范围、可恢复、可隔离的任务，例如临时测试目录、虚拟机、Docker、一次性工作空间。

### 企业场景不建议直接 Full Access

企业资料通常涉及合规、客户隐私、财务责任和内部权限边界。默认策略应是最小权限、人工确认、审计记录和可回滚。

## Template

```markdown
## Permission Decision Record

- Task:
- Workspace:
- Data sensitivity: public / internal / confidential / regulated
- Permission mode: default / Full Access
- Reason:
- High-risk operations:
- Backup location:
- Human approver:
- Rollback plan:
- Full Access close time:
```

## Further Reading

- [WorkBuddy 权限、安全与企业治理](README.md)
- [WorkBuddy 两个权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy 数据管理](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy Security Checklist](../templates/security-checklist.md)
- [Skill Evaluation Template](../templates/skill-evaluation-template.md)
- [Automation Design Template](../templates/automation-template.md)
