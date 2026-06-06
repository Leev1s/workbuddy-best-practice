# WorkBuddy Skill 实践指南

## TL;DR

Skill 用来扩展 WorkBuddy 的具体工具能力，例如读写文件、调用第三方 API、发送消息、查询数据或执行工作流。Skill 是能力，不是领域专家；启用 Skill 前应确认来源、权限、脚本内容、数据外发范围和可回滚方式。日常建议只启用当前任务需要的 Skill。

## Official facts

- WorkBuddy 官方文档说明，配置技能能够扩展 WorkBuddy 的能力范围。
- 官方定义 Skill 为增加“特定工具能力”的机制，封装一组可执行脚本与工作流，使 AI 在用户授权下完成具体动作。
- 官方示例包括发送邮件、订外卖、查询股价、读写文件、调用第三方 API 等。
- 技能板块包含“技能市场”和“已安装”：前者提供推荐技能并支持按需安装，后者展示已安装的本地技能。
- 官方说明支持上传本地技能包、按任务描述查找技能、按任务描述创建技能。
- 已安装 Skill 可关闭、重新启用或卸载；关闭后不会在对话中被调用。
- 官方提示非官方 Skill 可能存在恶意提示词注入、越权访问、后门程序等隐患，建议优先使用官方推荐 Skill。

## Practical interpretation

Skill 是把“模型会说”推进到“模型能做”的关键能力。一旦 Skill 能读写文件、调用 API 或控制外部服务，任务就从内容生成变成了真实操作。因此，Skill 的管理方式应接近软件依赖和企业工具授权，而不是普通 prompt 收藏。

不要把 Claude Code 的 Skill 机制直接等同于 WorkBuddy 官方 Skill。两者都可以作为“可复用能力”的方法论类比，但 WorkBuddy Skill 的安装、启用、权限和数据边界应以 WorkBuddy 官方文档与产品界面为准。

## How to use

1. 明确任务是否真的需要 Skill；只生成草稿或做分析时，不要额外启用工具型 Skill。
2. 从技能市场选择官方推荐或可信来源的 Skill。
3. 安装前检查用途、权限申请、脚本内容、第三方服务和数据外发说明。
4. 只启用当前任务需要的 Skill，完成后关闭不再需要的 Skill。
5. 第一次使用时选择低风险样本，确认输出和副作用。
6. 涉及删除、批量写入、对外发送、资金、账号或凭据时，要求 WorkBuddy 先列操作清单并等待确认。

## Best practices

- 把 Skill 当成“可执行依赖”管理：来源、版本、权限、用途都要记录。
- 每个高风险 Skill 建立评估表，记录允许使用的场景和禁止场景。
- 对文件类 Skill 使用临时工作空间和样本文件先测试。
- 对第三方 API Skill 检查调用额度、计费、隐私政策和失败处理。
- 对消息发送类 Skill 增加人工确认，避免误发到外部群、客户或上级。
- 对企业环境，优先建立允许清单，而不是让用户随意导入未知 Skill。

## Common mistakes

- 看到 Skill 能提升效率就长期全部启用。
- 安装第三方 Skill 前不看脚本和权限。
- 把“创建技能”当成无风险自动化，忽略生成脚本可能带来的副作用。
- 在真实资料上第一次试运行文件处理 Skill。
- 忽略 Skill 可能以用户本人身份执行操作。
- 把 Skill 当作官方事实来源，而不是工具能力。

## Security / permission notes

Skill 可能涉及账户身份信息、联系方式、用户输入、行为日志、第三方凭证、本地文件读写、屏幕与输入控制权限。实际范围取决于安装、启用和授权情况。

启用 Skill 前至少确认：

- 数据会不会发往第三方。
- 是否会读写本地文件或工作区外文件。
- 是否会执行系统命令或外部程序。
- 是否会代用户发送消息、邮件、请求或订单。
- 是否会使用 API Key、OAuth Token 或账号凭据。
- 是否有卸载、关闭、撤销授权和回滚方式。

## Template or checklist

```markdown
# Skill Evaluation

- Skill 名称：
- 来源：官方推荐 / 企业内部 / 第三方 / 未知
- 解决的问题：
- 需要的权限：
- 可能读取的数据：
- 可能写入或发送的数据：
- 是否调用第三方：
- 首次测试样本：
- 禁止使用场景：
- 回滚 / 关闭方式：
- 审批人：
```

## Further Reading

- [WorkBuddy 官方文档：技能](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Skills-Market)
- [WorkBuddy 官方文档：专家](https://www.codebuddy.cn/docs/workbuddy/From-Beginner-to-Expert-Guide/Function-Description/Expert-Center)
- [Skill Evaluation Template](../templates/skill-evaluation-template.md)
- [WorkBuddy Security Checklist](../templates/security-checklist.md)
- [sources.md](../sources.md)
