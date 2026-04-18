# ECC + Superpowers Stitch

这个仓库备份一种稳定的 Claude Code 插件整合方式：

- **Superpowers** 负责主流程
- **Everything Claude Code (ECC)** 保留为能力库
- 关闭 ECC 的重型 hook，避免和 Superpowers 的流程控制打架
- 只保留可显式调用的 ECC 能力

## 目标

这套方案解决的是“两个都很好用，但一起装容易重复编排、重复校验、重复 review、重复 hook”的问题。

最终原则只有一句话：

> 让 Superpowers 管怎么开发，让 ECC 管你还能调用哪些增强能力。

## 仓库内容

- `docs/integration-strategy.md`：整合原则与 owner matrix
- `docs/apply.md`：安装与落地步骤
- `docs/usage-rules.md`：日常使用规则
- `config/settings.example.json`：可直接参考的无密钥配置示例

## 快速应用

1. 安装 Superpowers

   ```bash
   /plugin install superpowers@claude-plugins-official
   ```

2. 添加 ECC marketplace

   ```bash
   /plugin marketplace add https://github.com/affaan-m/everything-claude-code
   ```

3. 安装 ECC

   ```bash
   /plugin install everything-claude-code@everything-claude-code
   ```

4. 将 `config/settings.example.json` 的相关字段合并到 `~/.claude/settings.json`
5. 重启 Claude Code

## 核心运行规则

- 非 trivial 开发，先走 `superpowers:brainstorming`
- 设计批准后，走 `superpowers:writing-plans`
- 执行阶段继续走 Superpowers 的执行 / TDD 链路
- 需要额外能力时，再显式调用 ECC 的 skill、agent 或命令
- 不要让 ECC 再接管默认 PreToolUse / PostToolUse / Stop 重型 hook

## 安全说明

这个仓库不包含任何 API key、token 或本机私有配置。

真实环境请不要直接提交你的 `~/.claude/settings.json`，而是只提交脱敏后的示例。
