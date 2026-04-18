# ECC + Superpowers Integration Strategy

## 主从结构

### 主流程：Superpowers

Superpowers 负责：

- brainstorming
- design approval
- writing-plans
- executing-plans / subagent-driven-development
- test-driven-development
- requesting-code-review

### 能力层：ECC

ECC 负责：

- 提供额外 commands / skills / agents
- 提供按需调用的工作流增强能力
- 不接管默认流程
- 不接管重型 hooks

## Owner Matrix

| 领域 | Owner |
|---|---|
| 需求澄清 | Superpowers |
| 设计批准 | Superpowers |
| 计划拆解 | Superpowers |
| 执行链路 | Superpowers |
| TDD 约束 | Superpowers |
| 额外能力调用 | ECC |
| 可选工具箱 | ECC |
| 默认重型 hooks | 关闭 ECC |

## 为什么要禁用 ECC 重 hook

ECC 的强项是 breadth 和自动化，但它的 PreToolUse / PostToolUse / Stop surface 很大。
如果和 Superpowers 的强流程叠加，典型后果是：

- 双规划
- 双 review
- 双验证
- 额外延迟
- 上下文噪音增加

因此最稳的做法是：

- 保留 ECC 插件
- 把 `ECC_HOOK_PROFILE` 压到 `minimal`
- 用 `ECC_DISABLED_HOOKS` 关闭重型 hook id

## 不打架规则

1. 只允许一个流程主人：Superpowers
2. ECC 只做显式调用，不做默认主控
3. 同一类 event/matcher 上，不让两边同时做决策型 hook
4. 不使用 Superpowers 的 deprecated generic commands
5. 文档单源：spec 和 plan 只认 Superpowers 产物

## 后续扩展

如果以后你想从 ECC 恢复部分能力，建议一条一条从 `ECC_DISABLED_HOOKS` 里移除，而不是一次性全开。
