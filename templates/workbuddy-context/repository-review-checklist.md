# Repository Review Checklist

适用场景：公开发布前审查 WorkBuddy best-practice 内容。  
风险等级：High。  
审批要求：涉及安全、权限、自动化、第三方服务或 Memory 的内容应由维护者复核。

## Content Accuracy

- [ ] 官方事实可追溯到 WorkBuddy 官方文档。
- [ ] 版本敏感内容已检查官方 Changelog。
- [ ] 实践建议没有写成官方事实。
- [ ] 没有大段复制官方文档原文。
- [ ] 第三方资料标注为“社区观察”或“第三方评价”。

## WorkBuddy Boundary

- [ ] 没有把 `.workbuddy/` 写成官方目录规范、强制目录或推荐目录。
- [ ] 没有声称 WorkBuddy 会自动读取 `.workbuddy/AI_AGENT_INSTRUCTIONS.md`。
- [ ] 没有把 repo 中的 Markdown memory 文件混同为 WorkBuddy 官方 Memory。
- [ ] Claude Code 的 `.claude/*`、commands、agents、skills、hooks、MCP 没有被写成 WorkBuddy 官方机制。

## Structure

- [ ] README 能说明项目定位、Start Here、学习路径、能力导航和免责声明。
- [ ] 章节 README 有导航价值。
- [ ] 新正文文件包含 Further Reading。
- [ ] 模板短、清晰、可复制。
- [ ] 无空 Markdown 文件。
- [ ] 无正文待办占位。
- [ ] 内部相对链接基本可访问。

## Security

- [ ] 删除、覆盖、批量移动、脚本执行、工作空间外写入和外部程序调用需要人工确认。
- [ ] Full Access 只作为可信、隔离、可恢复环境中的短时例外。
- [ ] Skill 风险覆盖来源、脚本、权限、提示词注入、数据外发和卸载。
- [ ] Connector 风险覆盖账号、授权范围、凭据、第三方协议、写操作和撤销。
- [ ] Automation 风险覆盖无人值守、日志、失败处理、低频试运行、首周监控和快速禁用。
- [ ] Memory 风险覆盖隐私、抽取偏差、编辑/删除和重要判断前核验。
- [ ] 自定义模型 / API 风险覆盖数据外发、费用、稳定性和密钥保存。

## Further Reading

- [WorkBuddy Security Checklist](../security-checklist.md)
- [WorkBuddy Context Convention](../../docs/workbuddy-context-convention.md)
- [sources.md](../../sources.md)
