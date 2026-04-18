# Usage Rules

## 默认工作姿势

### 1. 先设计，再计划，再执行

- `superpowers:brainstorming`
- `superpowers:writing-plans`
- `superpowers:executing-plans` 或 `superpowers:subagent-driven-development`
- `superpowers:test-driven-development`

### 2. ECC 只在需要时显式进入

适合交给 ECC 的事情：

- 特定 skill / agent 辅助
- 额外工具箱能力
- 某些专项工作流

不适合交给 ECC 的事情：

- 默认接管整个开发流程
- 在每轮响应后自动做第二套流程控制
- 重新定义设计 / 计划 / 执行主线

## 日常判断标准

如果一个动作会让 ECC 自动对 `Bash`、`Edit`、`Write`、`Stop` 再包一层默认控制，那它就不适合作为默认开启项。

如果一个动作只是让你多一个可显式调用的能力，它就适合作为 ECC 保留项。

## 最小冲突守则

- 规划只认 Superpowers
- 默认 review 节奏只认 Superpowers
- ECC 只做补强，不做抢权
- 恢复 ECC hook 时一次只恢复一个
