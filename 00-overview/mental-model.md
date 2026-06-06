# 办公 Agent 工程化心智模型

## TL;DR

本仓库的核心方法论是：先把办公任务变成可验收任务，再把可验收任务变成可复用流程，最后把可复用流程变成 Expert / Skill / Connector / Automation / Cloud Agent。不要从模糊需求直接跳到自动化；先手动跑通、验收、复盘，再做封装。

## Official facts

- WorkBuddy 官方文档说明其支持自然语言任务、自主规划执行、文件处理、结果查看、专家、技能、连接器、自动化、权限、记忆、模型和企业智能体等能力。
- 官方结果查看页面将产物、全部文件、变更和预览作为检查交付结果的重要入口。

## Practical interpretation

办公 Agent 工程化不是让 Agent 自由发挥，而是把任务设计成可执行、可观察、可验收、可复用、可治理的流程。

```text
Idea → Task Brief → Context Package → Manual Run → Result Review → Workflow Template → Expert / Skill / Connector → Automation → Cloud Agent
```

## The flow

### 1. Idea

用户有一个模糊办公需求，例如“帮我整理客户资料”或“做一份会议汇报”。这个阶段不要急着执行，先识别目标、受众、输入和风险。

### 2. Task Brief

把需求写成目标、输入、输出、约束、操作边界、验收标准和风险提醒。Task Brief 是办公 Agent 的最小工程资产。

### 3. Context Package

准备文件、背景资料、示例、规则、术语表、历史版本、品牌规范或数据字典。上下文质量决定执行质量。

### 4. Manual Run

先用普通任务手动跑通。手动阶段的目标不是追求自动化，而是验证任务描述是否清楚、输入是否足够、结果是否可验收。

### 5. Result Review

检查产物、全部文件、变更和预览。记录错误、遗漏、假设、权限提示和用户手工修正点。

### 6. Workflow Template

把稳定做法沉淀成模板：适用场景、输入要求、prompt、步骤、输出、验收清单、失败处理。

### 7. Expert / Skill / Connector

根据需求拆分：

- Expert：封装角色、判断标准和方法论。
- Skill：封装办公自动化、脚本、工作流或工具能力。
- Connector：连接外部系统、知识库、资料库或 MCP / CLI 类能力。

### 8. Automation

在流程稳定、输入可控、失败可处理后再定时化或批量化。Automation 需要监控、通知、人工审批和回滚方案。

### 9. Cloud Agent

当流程需要企业级生命周期管理、沙箱、版本、发布、协作和治理时，再升级到 Cloud Agent 视角。

## How to use

1. 对每个新需求先填 [Task Brief Template](../templates/task-brief-template.md)。
2. 第一次只做 Manual Run，不做 Automation。
3. 用 [Result Review Checklist](../templates/review-checklist.md) 验收。
4. 至少两到三次稳定后，再抽象为 workflow。
5. 进入 Skill / Connector / Automation 前完成安全评估。

## Best practices

- 先做小样本试跑，再做批量处理。
- 先生成清单，再执行删除、移动、覆盖。
- 先说明计划，再执行脚本。
- 先人工验收，再无人值守。
- 先记录风险，再推广给团队。

## Common mistakes

- 从 Idea 直接跳到 Automation。
- 只有 prompt，没有输入要求和验收标准。
- 只看最终回答，没有检查文件变更。
- 把一次成功当成稳定流程。
- 没有为失败、回滚、权限和数据隐私设计流程。

## Security / permission notes

流程越往后，自动化程度越高，风险也越高。Manual Run 阶段的风险通常可被用户及时发现；Automation 和 Cloud Agent 阶段则需要权限边界、日志、告警、回滚和审批机制。

## Template

```markdown
# Workflow Maturity Record

- Idea:
- Task Brief link:
- Context Package / `.workbuddy` path:
- Manual Run records:
- Review findings:
- Stable prompt:
- Candidate Expert / Skill / Connector:
- Automation readiness:
- Security approval:
```

## `.workbuddy/` boundary

`.workbuddy/` 可以帮助团队把 Context Package 文件化，但它只是本仓库的组织约定。WorkBuddy 官方 Memory 是产品从会话历史中提取并复用背景信息的能力，不等同于 `.workbuddy/memory/PROJECT_MEMORY.md`。

## Further Reading

- [WorkBuddy 官方简介](https://www.codebuddy.cn/docs/workbuddy/Overview)
- [WorkBuddy 结果查看](https://www.codebuddy.cn/docs/workbuddy/Results)
- [WorkBuddy 自动化](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [WorkBuddy 企业智能体](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent)
- [WorkBuddy 任务 Prompt 模板](../01-getting-started/task-prompt-template.md)
