# Skill Evaluation Template / Skill 评估模板

在启用、推荐或复用 WorkBuddy Skill 前复制本模板。尤其适合第三方 Skill、会访问本地文件的 Skill、会调用外部 API 的 Skill。目标是记录来源、权限、数据流、测试结果和审批边界。

## Basic Info

- Skill name:
- Version / release date:
- Maintainer:
- Business owner:
- Security reviewer:
- Evaluation date:
- Intended use case:

## Source

- Official / third-party / internal:
- URL or package source:
- Documentation:
- Update history:
- Trust notes:

## Permission Review

- Requested permissions:
- Why each permission is needed:
- Least-privilege alternative:
- Human confirmation required:
- Can be disabled without uninstalling: yes / no
- Should only be enabled during task execution: yes / no

## Data Flow

- Input data:
- Output data:
- Data stored locally:
- Data sent externally:
- Retention / deletion notes:

## Local File Access

- Read paths:
- Write paths:
- Delete / overwrite behavior:
- Batch operation behavior:
- Workspace isolation test:

## External API Access

- APIs / services called:
- Authentication method:
- Network domains:
- Data shared:
- Rate / cost implications:

## Script / Command Execution

- Commands executed:
- Runtime dependencies:
- System impact:
- Sandbox compatibility:
- Explanation provided before execution:
- Prompt injection risk reviewed:
- Backdoor / unexpected persistence reviewed:

## Risk Level

- Overall level: low / medium / high / blocked
- Main risks:
- Mitigations:
- Residual risk:

## Sandbox Test Result

- Test workspace:
- Test inputs:
- Expected behavior:
- Actual behavior:
- Unexpected files / network calls:
- Logs / evidence:

## Approval Decision

- Decision: approved / approved with restrictions / rejected / needs more review
- Approved scope:
- Restrictions:
- Prohibited data:
- Prohibited operations:
- Reviewer:
- Expiration / re-review date:

## Further Reading

- [WorkBuddy 技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy 权限、安全与企业治理](../08-permission-security/README.md)
- [WorkBuddy Security Checklist](security-checklist.md)
