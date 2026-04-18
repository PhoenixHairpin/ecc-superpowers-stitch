# Customize This Template

## 你可以改哪些部分

### 1. 保持不动的核心

建议不要改：

- Superpowers 作为主流程 owner
- ECC 默认只做能力补充
- `ECC_HOOK_PROFILE` 保持 `minimal`
- 默认关闭 ECC 重型 hook

### 2. 可以按需调整的部分

#### A. 恢复某个 ECC hook

如果你真的需要某个 ECC 能力，优先做法是：

- 从 `ECC_DISABLED_HOOKS` 中删掉一个 hook id
- 重启 Claude Code
- 观察是否重新出现重复流程、重复提醒或额外噪音

一次只恢复一个。

#### B. 项目级配置

如果你不想影响所有项目，可以把规则落到项目级 `.claude/settings.json`。

参考：

- `config/project.settings.example.json`
- `templates/CLAUDE.example.md`

#### C. 团队协作说明

你可以在项目仓库里增加：

- 什么时候必须先 brainstorm
- 哪些任务允许直接实现
- 哪些 ECC 能力允许显式调用

## 不建议做的事

- 同时让 ECC 和 Superpowers 默认接管 `Bash|Edit|Write|Stop`
- 重新打开 ECC 全量自动流程
- 使用 Superpowers 的 deprecated generic commands
- 同时维护两套 plan/spec 文档体系

## 推荐演进方式

### 阶段 1：稳定期

- Superpowers 主流程
- ECC 能力库模式
- ECC hooks 基本关闭

### 阶段 2：选择性恢复

- 观察缺什么能力
- 按 hook id 单个恢复
- 保留单主人原则

### 阶段 3：团队规范化

- 把可接受的恢复项写入项目 CLAUDE.md
- 形成团队统一约束
