# Automation Design Template / Automation 设计模板

仅在工作流已人工运行并通过验收后使用本模板。它用于把稳定任务整理成可定时、可触发、可回滚的 Automation 设计。涉及删除、覆盖、外部分享或无人值守执行时，应先完成安全审批。

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

- Trigger type: schedule / event / manual approval / other
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
