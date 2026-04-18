# ECC + Superpowers Stitch Template

中文 | [English](README.en.md)

这是一个**可直接 fork** 的模板仓库，用来保存并复用一套稳定的 Claude Code 插件整合方案。

目标不是同时让两个插件都当“默认主控”，而是固定成：

- **Superpowers** = 主流程
- **Everything Claude Code (ECC)** = 显式能力库

这样可以避免：

- 双规划
- 双 review
- 双验证
- 重型 hooks 叠加
- 上下文噪音和响应延迟上升

## 模板内容

### 中文文档

- `docs/zh/integration-strategy.md`
- `docs/zh/apply.md`
- `docs/zh/usage-rules.md`
- `docs/zh/customize.md`
- `docs/zh/checklist.md`

### English docs

- `docs/en/integration-strategy.md`
- `docs/en/apply.md`
- `docs/en/usage-rules.md`
- `docs/en/customize.md`
- `docs/en/checklist.md`

### Shared config/templates

- `config/settings.example.json`
- `config/project.settings.example.json`
- `templates/CLAUDE.example.md`
- `.gitignore`

## 一句话原则

> 让 Superpowers 管怎么开发，让 ECC 管你还能调用哪些增强能力。

## 推荐工作流

1. `superpowers:brainstorming`
2. `superpowers:writing-plans`
3. `superpowers:executing-plans` 或 `superpowers:subagent-driven-development`
4. `superpowers:test-driven-development`
5. 只有在需要额外能力时，才显式调用 ECC

## 快速开始

### 1. Fork 本仓库

把它作为你自己的整合模板仓库。

### 2. 安装插件

```bash
/plugin install superpowers@claude-plugins-official
/plugin marketplace add https://github.com/affaan-m/everything-claude-code
/plugin install everything-claude-code@everything-claude-code
```

### 3. 合并配置

把 `config/settings.example.json` 的相关字段合并进你的 `~/.claude/settings.json`。

如果某个项目需要单独控制，再参考 `config/project.settings.example.json`。

### 4. 重启 Claude Code

插件启用与环境变量都依赖重启。

## 安全说明

仓库中只放**脱敏示例**，不放：

- API keys
- auth tokens
- 完整个人 `settings.json`
- 本机路径或私有服务地址
