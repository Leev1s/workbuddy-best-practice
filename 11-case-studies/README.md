# Case Studies

本章收集可复制的 WorkBuddy 办公案例。案例类型来自 WorkBuddy 官方文档列出的常见办公场景和实践案例导航，再转写成更适合企业内部复用的 task brief、工作流、验收标准和风险提醒。

本章不是 WorkBuddy 官方案例镜像。案例中的 workflow 属于实践解释；具体入口、按钮、能力可用性和授权范围应以官方文档、当前产品界面和企业内部权限规则为准。

## Case Index

| Case | Enterprise value | Output | Required capability | Main risk |
|---|---|---|---|---|
| [批量文件识别与归档](batch-file-organization.md) | 降低文件命名和交接错误 | 文件清单、重命名预览、归档方案 | 工作目录、本地文件处理、结果验收 | 误删、覆盖、越界移动 |
| [会议记录整理为纪要和行动项](meeting-minutes-action-items.md) | 减少会后整理和责任遗漏 | 会议纪要、行动项表、待确认事项 | 文件输入、文档生成；可选会议相关 Skill / Connector | 个人信息、未确认结论、外发 |
| [项目汇报文档与 PPT 生成](project-report-and-ppt.md) | 提升汇报材料结构化和一致性 | 汇报文档、PPT 大纲或 PPTX | 文档生成、PPT / Office Skill 可选 | 未授权承诺、第三方导出 |
| [业务数据分析与可视化报告](data-analysis-visual-report.md) | 提高数据复盘效率和可审计性 | 分析报告、图表、汇总表 | 表格处理、图表生成；脚本可选 | 数据口径错误、PII、模型/API 外发 |
| [每日资讯简报自动化](daily-briefing-automation.md) | 减少重复信息收集和分发 | 简报文件、推送记录、异常清单 | Automation、指定来源、可选 Connector | 误发、来源不可信、无人值守失败 |

## Case Contract

每个案例都应包含：

- 企业价值：节省时间、降低错误、提升审计性或减少交接成本。
- 适用 / 不适用场景：说明哪些任务可以复用，哪些任务不应自动化。
- 前置条件：工作空间、文件副本、已安装 Skill / Connector、授权账号、权限模式。
- 可复制 task brief：包含目标、输入、输出、边界、验收和停止条件。
- 人工确认点：预览后、外发前、覆盖/删除前、自动化上线前。
- 审计证据：产物、清单、日志、审批记录、失败说明和回滚路径。

## Usage

1. 先复制案例中的 task brief，再替换输入材料、输出格式、范围和验收标准。
2. 第一次运行只处理小样本，确认命名规则、报告结构或推送内容正确后再扩大范围。
3. 涉及文件写入、删除、脚本执行、Connector、Automation 和第三方服务时，优先使用默认权限，并把输入材料放在独立工作空间。
4. 每个案例都保留人工验收环节，不把 WorkBuddy 输出直接作为最终业务结论或自动发送内容。
5. 使用 [Task Brief Template](../templates/task-brief-template.md)、[Review Checklist](../templates/review-checklist.md)、[Security Checklist](../templates/security-checklist.md) 和 [Automation Template](../templates/automation-template.md) 补齐企业审批字段。

## Further Reading

- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 创建任务](https://www.codebuddy.cn/docs/workbuddy/Create-Task)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy 高效使用小技巧](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Efficient-Tips)
- [WorkBuddy 权限模式](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Permission-Modes)
