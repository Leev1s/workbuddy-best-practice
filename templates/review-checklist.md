# WorkBuddy Result Review Checklist / 结果验收清单

在接受、转发或归档 WorkBuddy 输出前使用本清单。它帮助检查任务目标、输入覆盖、文件安全、外部服务和人工审批是否到位。用于自动化前，请先完成至少一次人工验收。

## Task Understanding

- [ ] The result matches the original goal.
- [ ] WorkBuddy did not silently change the scope.
- [ ] Open questions and assumptions are listed.
- [ ] The result is suitable for the target audience.

## Input Coverage

- [ ] All required files were used.
- [ ] No unintended files were used.
- [ ] Data time range is correct.
- [ ] Missing data is explicitly noted.
- [ ] Conclusions can be traced to inputs.

## Output Quality

- [ ] Output format is correct.
- [ ] File naming is clear.
- [ ] Structure is easy to review.
- [ ] Facts, numbers, and references are checked.
- [ ] Tone and level of detail match the scenario.

## File Safety

- [ ] Files are written to the expected workspace.
- [ ] Original files are not modified unless explicitly allowed.
- [ ] No unexpected deletion, overwrite, move, or rename happened.
- [ ] Batch operations have a reviewed inventory or plan.
- [ ] Backup exists for important files.

## Data Privacy

- [ ] Sensitive data is identified.
- [ ] Personal data, customer data, financial data, secrets, and credentials are handled appropriately.
- [ ] Unnecessary data is not included in outputs.
- [ ] Outputs are safe to share with the intended audience.

## External Services

- [ ] External API / Connector / Skill usage is listed.
- [ ] Data sent outside the workspace is understood.
- [ ] Third-party terms and enterprise policies are considered.
- [ ] Credentials or tokens are not exposed.

## Automation Readiness

- [ ] The task has been manually run and reviewed.
- [ ] Failure conditions are known.
- [ ] Notifications are planned.
- [ ] Rollback or recovery exists.
- [ ] Human approval points are defined.

## Human Approval

- [ ] Reviewer:
- [ ] Approval date:
- [ ] Approved for: personal use / team sharing / external sharing / automation
- [ ] Required changes before approval:

## Further Reading

- [WorkBuddy 结果验收指南](../01-getting-started/result-review.md)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy Security Checklist](security-checklist.md)
