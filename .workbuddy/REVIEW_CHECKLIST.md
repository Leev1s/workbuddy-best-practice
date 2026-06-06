# Repository Review Checklist

本清单用于审查 `workbuddy-best-practice` 仓库内容是否达到可公开发布标准。`.workbuddy/` 是本仓库的实践约定，用于项目级上下文、prompt、workflow、review checklist 和稳定项目记忆；它不是 WorkBuddy 官方规范，也不代表 WorkBuddy 会自动读取这些文件。

## Content accuracy

- [ ] 官方事实是否可追溯到 WorkBuddy 官方文档？
- [ ] 版本敏感内容是否检查了官方 Changelog？
- [ ] 是否避免把实践建议写成官方事实？
- [ ] 是否避免大段复制官方文档原文？
- [ ] 是否把第三方资料明确标注为“社区观察”或“第三方评价”？

## `.workbuddy/` boundaries

- [ ] 是否明确 `.workbuddy/` 是本仓库实践约定？
- [ ] 是否避免声称 WorkBuddy 会自动读取 `.workbuddy/`？
- [ ] 是否避免把 `memory/PROJECT_MEMORY.md` 等同于官方 Memory？
- [ ] 是否没有写入私密上下文、缓存、日志、任务产物或敏感信息？

## Structure

- [ ] 新增文章是否有 `Further Reading`？
- [ ] README 或章节 README 是否补充导航？
- [ ] 模板是否可直接复制使用？
- [ ] 是否不存在空 Markdown 文件？
- [ ] 是否不存在只含占位符的正文？
- [ ] 内部相对链接是否基本可访问？

## Safety

- [ ] 涉及文件、权限、Skill、Connector、Automation、Cloud Agent 的内容是否包含风险提醒？
- [ ] 是否标注第三方资料为“社区观察”或“第三方评价”？
- [ ] 是否把默认权限写成日常基线，而不是把 Full Access 当作默认建议？
- [ ] 是否说明 Full Access 只适合可信、隔离、可恢复的短时任务？
- [ ] 是否对删除、覆盖、批量移动、脚本执行、外部程序调用写出人工确认要求？
- [ ] Skill 内容是否提醒非官方 Skill 的提示词注入、越权访问和后门风险？
- [ ] Connector 内容是否提醒授权凭据、第三方业务数据、外部写操作和撤销授权？
- [ ] Automation 内容是否提醒无人值守、日志、失败处理、低频试运行和快速禁用？
- [ ] Memory 内容是否提醒隐私、用户控制、抽取偏差和重要判断前核验？
- [ ] 数据管理内容是否提醒分享文件可撤销、归档任务可管理、敏感文件分享前需复核？

## Enterprise governance

- [ ] 是否有明确的数据分类：public / internal / confidential / regulated？
- [ ] 是否有任务 owner、审批人、回滚 owner 或 incident contact？
- [ ] 是否有备份、回滚、审计记录或日志保留建议？
- [ ] 是否避免要求用户把 API Key、Token、Cookie、客户资料或私人上下文写入仓库？
- [ ] 是否避免把 `.workbuddy/memory/PROJECT_MEMORY.md` 写成官方 Memory 或敏感信息存放处？

## Further Reading

- [WorkBuddy 权限、安全与企业治理](../08-permission-security/README.md)
- [WorkBuddy Result Review Checklist](../templates/review-checklist.md)
- [WorkBuddy Security Checklist](../templates/security-checklist.md)
