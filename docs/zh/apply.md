# Apply the Integration

## 1. 安装插件

```bash
/plugin install superpowers@claude-plugins-official
/plugin marketplace add https://github.com/affaan-m/everything-claude-code
/plugin install everything-claude-code@everything-claude-code
```

## 2. 合并配置

将 `config/settings.example.json` 中这几类字段合并到你的 `~/.claude/settings.json`：

- `extraKnownMarketplaces`
- `enabledPlugins`
- `env.ECC_HOOK_PROFILE`
- `env.ECC_DISABLED_HOOKS`

不要用示例文件覆盖你现有的密钥、模型、主题、权限等个人设置。

## 3. 重启 Claude Code

插件启用和环境变量生效都依赖重启。

## 4. 验证方式

验证标准：

- Superpowers 仍然是主流程
- ECC 已安装且可按需调用
- ECC 不再自动跑一整套 PreToolUse / PostToolUse / Stop 重型 hook

## 5. 需要恢复 ECC 某个 hook 时

从 `ECC_DISABLED_HOOKS` 里删除对应 id，然后重启 Claude Code。

建议一次只恢复一个，观察是否重新出现重复流程或噪音。
