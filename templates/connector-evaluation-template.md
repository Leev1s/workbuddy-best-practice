# Connector Evaluation Template / Connector 评估模板

用于 WorkBuddy Connector 上线、授权、扩权或接入企业系统前的评估。连接器通常以用户授权身份访问第三方服务，因此必须先确认账号、权限、数据流、写操作和撤销方式。

## Basic Info

- Connector name:
- Official / custom / third-party:
- Service provider:
- Business owner:
- Account owner:
- Security reviewer:
- Evaluation date:
- Intended workflow:

## Authorization

- Auth method: OAuth / API key / token / other
- Authorized account:
- Permission scope:
- Read permissions:
- Write permissions:
- Admin permissions:
- Revoke path:
- Rotation / expiration policy:

## Data Access

- Third-party account identifiers accessed:
- Business data read:
- Business data written:
- Attachments / files accessed:
- Data sent back to WorkBuddy:
- Data sent to other services:
- Retention / deletion expectation:

## Permission Boundary

- Does it operate only within the user's existing third-party permission scope?
- Does each connector require independent authorization?
- Can it be disabled from WorkBuddy?
- Can authorization be revoked from the third-party service?
- Custom connector access range documented:

## External Actions

- Can send messages / emails:
- Can create / edit documents:
- Can create meetings / tasks / tickets:
- Can upload / download files:
- Can trigger downstream automations:
- Human approval required before write actions:

## Enterprise Controls

- Approved users / groups:
- Approved workspaces:
- Allowed data classifications:
- Prohibited data classifications:
- Logging / evidence location:
- Incident owner:
- Third-party service status / SLA reviewed:
- Third-party terms / privacy reviewed:

## Test Result

- Test workspace:
- Test account:
- Test inputs:
- Expected behavior:
- Actual behavior:
- Unexpected data access:
- Unexpected write action:
- Revocation test result:

## Approval Decision

- Decision: approved / approved with restrictions / rejected / needs more review
- Approved scope:
- Restrictions:
- Required human confirmations:
- Reviewer:
- Expiration / re-review date:

## Further Reading

- [WorkBuddy 连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 权限、安全与企业治理](../08-permission-security/README.md)
- [WorkBuddy Security Checklist](security-checklist.md)
