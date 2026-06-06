# WorkBuddy 模型与记忆实践指南

## TL;DR

模型配置决定任务的能力、速度、成本和数据流向；记忆决定 WorkBuddy 是否会把过往会话中的偏好和事实作为后续上下文。企业使用时要把二者分开治理：模型关注 API Key、本地配置、第三方协议和费用；记忆关注隐私、准确性、可编辑、可删除和是否适合被长期保留。

## Official facts

- WorkBuddy 官方文档说明，产品内置主流大模型，覆盖推理、多模态及图像处理能力，并支持自定义模型。
- 自定义模型可通过可视化界面添加、编辑和删除；配置参数包含 API Key。
- 官方说明模型配置保存在本地 `workbuddy/models.json` 中，不上传云端。
- 使用自定义模型时，WorkBuddy 作为通信链路，将输入直接转发至所配置的第三方模型，输出由该模型返回。
- 自动模式 Auto 启用后，WorkBuddy 会根据任务自动选择适合的模型。
- 记忆功能会从会话历史中提取有参考价值的信息，形成记忆数据并定期更新。
- 官方说明记忆每晚整理当天会话，仅用户本人可见；可在设置中查看、编辑、删除或关闭，也支持从其他 AI 导入记忆。
- 官方说明记忆功能不额外消耗用户 token / 积分，记忆数据用于产品内部为本人提供个性化服务。

## Practical interpretation

模型选择是任务策略的一部分。日常文档和办公分析可以优先使用 Auto 或均衡模型；复杂推理、多模态输入、长文档整理、代码或图像任务应按实际能力选择。自定义模型适合企业已有模型采购、内网合规、本地部署或成本控制，但需要承担第三方模型的稳定性、合规性和费用风险。

记忆不是项目知识库，也不是企业制度库。它更适合保存个人偏好、常用表达、固定协作习惯和近期跟进事项。需要公开、稳定、可审计的项目上下文，应放在项目文档或本仓库 `.workbuddy/` 这类人工维护的 context folder 中，而不是依赖个人记忆。

## How to use

1. 普通任务先用 Auto；遇到效果、速度、成本或多模态需求时再切换模型。
2. 接入自定义模型前，确认供应商、API Key、费用、隐私政策、可用能力和退出方案。
3. 对敏感数据任务，优先确认数据是否会发送到第三方模型。
4. 定期检查本地模型配置，删除不用的 API Key。
5. 使用记忆时，定期查看记忆条目，删除不准确、过期或不应长期保留的信息。
6. 对项目级规则，用明确文档维护，不依赖个人记忆自动抽取。

## Best practices

- 把模型选择写进任务复盘：模型、原因、效果、成本、是否适合复用。
- 自定义模型 API Key 不写入公开仓库、共享文档或 prompt。
- 本地部署模型适合隐私敏感、内网或离线场景，但要接受能力和硬件限制。
- 记忆只保留稳定偏好，不保留临时任务日志、客户隐私、密钥、账号或敏感人事信息。
- 依赖记忆做判断前先核验，因为自动抽取可能存在概括偏差或时效性问题。
- 团队知识应进入可审计的知识库、项目文档或模板，而不是个人记忆。

## Common mistakes

- 只追求最强模型，不考虑任务成本和数据流向。
- 把自定义模型接入后，忘记第三方模型会按其协议处理输入内容。
- 在共享电脑或公共环境保存 API Key。
- 把记忆当成准确无误的事实库。
- 让记忆保存不该长期存在的私人信息、客户信息或临时上下文。
- 混淆本仓库 `.workbuddy/memory/PROJECT_MEMORY.md` 与 WorkBuddy 官方 Memory；前者只是本仓库人工维护的项目约定。

## Security / permission notes

模型配置的主要风险是凭据和数据外发。API Key 是访问第三方模型账号的关键凭据，应妥善保管并定期清理。自定义模型由第三方独立运营，其可用性、安全性、合规性、费用和输出结果需要按第三方协议评估。

记忆的主要风险是隐私和误用。会话中包含他人个人信息、客户资料或商业秘密时，应确认提交和记忆使用是否符合授权与企业规则。删除或关闭记忆后，后续对话会停止使用相关数据，但已生成输出不会被追溯撤回。

## Template or checklist

```markdown
# Model and Memory Decision

- 任务：
- 模型：Auto / 内置模型 / 自定义模型 / 本地模型
- 选择原因：
- 是否包含敏感数据：
- 数据是否发往第三方模型：
- API Key 保存位置：
- 预估成本：
- 是否允许使用记忆：
- 需要删除或更正的记忆：
- 项目级上下文文档：
```

## Further Reading

- [WorkBuddy 官方文档：模型配置](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Model)
- [WorkBuddy 官方文档：记忆](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Memory)
- [WorkBuddy 官方文档：数据管理](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Data-Management)
- [`.workbuddy` 项目级上下文目录指南](../01-getting-started/project-context-directory.md)
- [sources.md](../sources.md)
