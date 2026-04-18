# Fork Checklist

## Fork 后先做这些

- [ ] 修改仓库描述
- [ ] 按需要改成 private 或 public
- [ ] 阅读 `docs/integration-strategy.md`
- [ ] 阅读 `docs/customize.md`
- [ ] 决定是用全局设置还是项目级设置
- [ ] 合并 `config/settings.example.json`
- [ ] 重启 Claude Code

## 校验是否生效

- [ ] Superpowers 仍然是默认主流程
- [ ] ECC 已启用并可显式调用
- [ ] ECC 不再默认跑重型 Pre/Post/Stop hooks
- [ ] 没有出现双规划或双 review

## 如果想继续扩展

- [ ] 新增你自己的 CLAUDE 模板
- [ ] 新增团队使用规则
- [ ] 记录哪些 ECC hook 可以安全恢复
