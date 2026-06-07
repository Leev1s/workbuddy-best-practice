# Automation Design Template / Automation 设计模板

仅在工作流已人工运行并通过验收后使用本模板。它用于把稳定任务整理成可定时、可回滚的 Automation 设计。涉及删除、覆盖、外部分享或无人值守执行时，应先完成安全审批。

## Quick Go / No-Go

- Go: 周期性、重复性、输入稳定、输出可验收、失败可停止、结果不自动外发高风险对象。
- No-Go: 规则不清、数据敏感且未审批、需要实时人工判断、涉及资金 / 法务承诺 / 删除覆盖、失败会持续误发。
- Needs review: 需要 Skill / Connector、自定义模型 API、Full Access、第三方系统写入或对外发送。

## Minimal Automation Prompt

```markdown
请按以下规则执行定时任务：

目标：
输入范围：
输出文件：
禁止操作：
失败停止条件：
完成后请列出产物、来源、异常和需要人工复核的事项。
```

## Task Name

- Name:
- Owner:
- Security owner:
- Business process:

## Purpose

- What business outcome should this automation produce?
- Why should it be automated instead of manually triggered?
- What is the expected time saved or quality improvement?

## Trigger / Schedule

- Schedule type: fixed time / recurring interval / current product UI option
- Non-scheduled trigger: not assumed; verify against current WorkBuddy UI and official docs before writing as a capability
- Frequency:
- Time zone:
- Holiday / exception rules:
- Low-frequency trial period:
- Maximum acceptable execution time:

## Workspace

- Workspace path:
- Input folder:
- Output folder:
- Archive folder:
- Backup location:

## Prompt

```markdown
[Paste the stable WorkBuddy task prompt here.]
```

## Required Skills / Connectors

- Skills:
- Connectors:
- External APIs:
- Credentials / accounts:
- Permission mode:
- Connector authorization owner:
- Skill evaluation completed: yes / no

## Expected Output

- Files:
- Notifications:
- Reports:
- Logs:
- Success criteria:

## Failure Handling

- Known failure modes:
- Retry policy:
- Alert recipient:
- Escalation path:
- Safe stop condition:
- Quick disable path:
- Evidence / logs to keep:
- First-week monitoring: after each scheduled run, verify trigger history, output directory, failure logs, and whether any external notification was sent.

## Human Review Required?

- Before execution: yes / no
- Before external sharing: yes / no
- Before deletion / overwrite: yes / no
- Before creating / editing third-party records: yes / no
- Before sending messages / emails: yes / no
- Reviewer:
- Approval SLA:

## Prohibited Actions

- Delete files without reviewed inventory:
- Overwrite files without backup:
- Send external messages without approval:
- Move money / place orders / submit legal commitments:
- Store secrets in prompt or output:

## Rollback Plan

- How to restore files:
- How to disable automation:
- How to revert external changes:
- Recovery owner:

## Cost / Token Notes

- Expected model usage:
- External API cost:
- Peak schedule risk:
- Budget owner:

## Further Reading

- [WorkBuddy 自动化](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [WorkBuddy 连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 结果验收指南](../01-getting-started/result-review.md)
- [WorkBuddy Security Checklist](security-checklist.md)
