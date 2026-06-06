# WorkBuddy Cloud Agent 实践指南

## TL;DR

Cloud Agent 面向企业智能体场景，用于把 Agent 配置、运行环境、渠道接入、凭据、Session、Runtime 和评测组织成可管理的服务。它适合团队共享和系统集成，但也带来更高治理要求：版本、凭据、渠道、沙箱、会话文件、删除风险和评测成本都要纳入运维流程。

## Official facts

- WorkBuddy 官方 Cloud Agent 页面介绍企业智能体相关能力，包括 Agent 配置、渠道接入、凭据管理、Agent 管理、Runtime、Session 和 Agent 评测。
- 官方说明 Agent 配置中可包含工作区信息、仓库或源码包、分支 / 标签 / Commit SHA、初始化命令、环境变量和 secrets。
- 官方提示 secrets 支持通过环境变量引用，避免硬编码密钥；敏感信息通过安全通道注入，不写入沙箱文件。
- Cloud Agent 支持接入企微 AIBot、QQ 机器人、飞书和钉钉，用于接收和回复 Agent 消息。
- 凭据管理用于为 Agent 提供安全凭据存储和代理注入；凭据以加密方式存储，仅在 Agent 运行时由代理层解密并注入请求头。
- 管理 Agent 时可进行接入、版本管理、编辑、克隆、删除等操作；接入链接可让团队成员获得独立 Session，也支持 API 集成。
- Runtime 页面展示沙箱运行状态；Session 承载用户对话记录和产出文件，超过 10 分钟无访问会自动休眠并可再次唤醒。
- 官方警告删除 Session 将永久清除对话记录和文件；Agent 评测会消耗个人积分。

## Practical interpretation

Cloud Agent 是把个人任务能力产品化、服务化的一步。它不只是“把 prompt 分享给同事”，而是把 Agent 的配置、运行环境、凭据、渠道和评测集中管理。适合企业内部助手、流程入口、部门知识服务、系统集成和固定场景的办公自动化。

与本地 WorkBuddy 任务相比，Cloud Agent 更需要工程治理：谁能改配置、谁能发布版本、哪些渠道可接入、凭据如何轮换、Session 删除怎么审批、失败如何排查、评测数据怎么维护。

## How to use

1. 先从单人可复现任务开始，整理任务说明、输入边界和输出标准。
2. 设计 Agent 配置，包括工作区、初始化命令、环境变量、secrets 和可用工具。
3. 在 Test Run 模式中验证响应质量和边界行为。
4. 配置渠道接入前，确认消息来源、可见范围和团队使用规则。
5. 通过凭据管理注入外部服务认证，不在代码、prompt 或配置正文中明文写密钥。
6. 发布前建立版本说明和回滚方案。
7. 使用 Runtime、Session 和评测结果持续排查质量、稳定性和成本。

## Best practices

- 将 Cloud Agent 看作企业应用，而不是一次性对话。
- 每个 Agent 建立 owner、适用场景、禁止场景、数据范围和升级路径。
- secrets 使用安全通道注入，避免硬编码到仓库、manifest、prompt 或脚本。
- 接入企业微信、飞书、钉钉等渠道前，先定义响应边界和人工兜底方式。
- 版本发布前进行 Test Run 和小范围试点。
- 定期清理无关联或不再使用的 Runtime 和 Session。
- 删除 Session 前确认是否需要导出或留存对话记录和产出文件。
- 用标准化评测任务衡量能力，不只靠单次主观体验。

## Common mistakes

- 把个人可用的 prompt 直接发布成团队 Agent。
- 在配置或脚本里明文写入 API Key、Token 或账号密码。
- 没有版本管理和回滚策略就频繁修改生产 Agent。
- 忽略每个用户会获得独立 Session，导致排查时混淆上下文。
- 删除 Session 前没有意识到对话记录和文件会永久清除。
- 只关注接入渠道，不关注凭据、沙箱、日志、评测和成本。

## Security / permission notes

Cloud Agent 的风险边界包括：

- secrets、API Key、Token 和外部服务凭据。
- 工作区代码、初始化命令和运行环境变量。
- 企业即时通讯渠道中的用户消息和回包内容。
- Session 中的对话历史和产出文件。
- API 集成带来的调用身份和访问范围。
- Agent 版本变更对团队用户的影响。

企业落地时应设置最小权限、凭据轮换、配置审批、版本审计、渠道准入、Session 删除审批和评测数据管理。涉及客户资料、合同、财务、人事、生产系统或外部发送时，应增加人工确认和日志留存。

## Template or checklist

```markdown
# Cloud Agent Release Checklist

- Agent 名称：
- Owner：
- 使用场景：
- 禁止场景：
- 工作区 / 仓库：
- 初始化命令：
- 环境变量：
- Secrets：
- 接入渠道：
- 凭据负责人：
- Test Run 结论：
- 版本说明：
- 回滚方案：
- Session 保留策略：
- 评测数据集：
```

## Further Reading

- [WorkBuddy 官方文档：Cloud Agent](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/CloudAgent)
- [WorkBuddy 官方文档：连接器](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Connector)
- [WorkBuddy 官方文档：技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy 官方文档：自动化](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Automation-Guide)
- [sources.md](../sources.md)
