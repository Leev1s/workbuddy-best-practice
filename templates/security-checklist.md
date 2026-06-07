# WorkBuddy Security Checklist / 安全检查清单

在任务涉及文件操作、权限模式、Skill、Connector、外部服务或 Automation 前使用本清单。它不是合规审计报告，而是团队执行前的最低安全确认。企业敏感数据、生产文件和无人值守流程需要更严格的内部审批。

## Workspace

- [ ] The task uses a dedicated workspace.
- [ ] Only necessary files are included.
- [ ] Important files are copied, not processed as unique originals.
- [ ] Output folder is explicit.
- [ ] Workspace is not desktop, downloads root, personal document root, or production repo root unless intentionally approved.
- [ ] If a local `.workbuddy/` experiment exists, it is excluded from the public repo and labeled as a repository convention.

## File Operations

- [ ] Read scope is clear.
- [ ] Write scope is clear.
- [ ] Delete / overwrite operations require human approval.
- [ ] Batch operations have a preview inventory.
- [ ] Backups exist for important files.

## Permission Mode

- [ ] Default permission is used for normal tasks.
- [ ] Full Access is avoided for enterprise / sensitive tasks.
- [ ] If Full Access is required, the environment is isolated and recoverable.
- [ ] Full Access business reason, approver, backup, rollback plan, and close time are recorded.
- [ ] Permission decision has an owner.

## Skill / Connector

- [ ] Skill / Connector source is known.
- [ ] Requested permissions are reviewed.
- [ ] External APIs and data flows are understood.
- [ ] Third-party components are not assumed trustworthy.
- [ ] Sandbox test is completed for risky components.
- [ ] Non-official Skills have been reviewed for prompt injection, unexpected file access, external calls, and scripts.
- [ ] Connectors have an owner, authorization scope, revoke path, and write-operation approval rule.

## Memory

- [ ] Sensitive personal, customer, financial, legal, credential, and regulated data is not intentionally written into conversation for memory.
- [ ] Memory-dependent facts are verified against source materials before important decisions.
- [ ] Users know where to view, edit, delete, or disable memory.

## Data Privacy

- [ ] Sensitive data is classified.
- [ ] Personal, customer, financial, contract, credential, and regulated data are minimized.
- [ ] Secrets and tokens are not included in prompts or outputs.
- [ ] Data retention and deletion expectations are clear.
- [ ] Shared files are reviewed before sharing and cancelled when no longer needed.

## External Sharing

- [ ] External sharing is explicitly allowed.
- [ ] Recipient scope is correct.
- [ ] Generated files are reviewed before sharing.
- [ ] Watermarks, labels, or confidentiality notices are added if needed.

## Automation

- [ ] Manual runs have been successful and reviewed.
- [ ] A low-frequency trial run has been completed before increasing schedule frequency.
- [ ] Failure handling exists.
- [ ] Notifications and logs are configured.
- [ ] Human approval gates are defined.
- [ ] Automation can be disabled quickly.
- [ ] Unattended file deletion, overwrite, funds movement, and external sending are blocked or require explicit approval.

## Recovery

- [ ] Backup location:
- [ ] Restore procedure:
- [ ] Rollback owner:
- [ ] Incident contact:
- [ ] Post-incident review process:

## Further Reading

- [WorkBuddy 权限、安全与企业治理](../08-permission-security/README.md)
- [WorkBuddy 两个权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
- [WorkBuddy 数据管理](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data)
- [WorkBuddy 连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 自动化](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [Skill Evaluation Template](skill-evaluation-template.md)
- [Connector Evaluation Template](connector-evaluation-template.md)
- [Automation Design Template](automation-template.md)
