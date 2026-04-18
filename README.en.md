# ECC + Superpowers Stitch Template

[中文](README.md) | English

This is a **forkable template repository** for preserving and reusing a stable Claude Code plugin integration pattern.

The goal is **not** to let both plugins act as default orchestrators. Instead, the template locks in this split:

- **Superpowers** = primary workflow owner
- **Everything Claude Code (ECC)** = explicit capability library

This avoids:

- duplicate planning
- duplicate reviews
- duplicate verification loops
- stacked heavy hooks
- extra latency and context noise

## Template contents

### Chinese docs

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

## One-line principle

> Let Superpowers own how development happens, and let ECC provide extra capabilities only when explicitly invoked.

## Recommended workflow

1. `superpowers:brainstorming`
2. `superpowers:writing-plans`
3. `superpowers:executing-plans` or `superpowers:subagent-driven-development`
4. `superpowers:test-driven-development`
5. Only invoke ECC when you need extra capability

## Quick start

### 1. Fork this repository

Use it as your own integration template repository.

### 2. Install the plugins

```bash
/plugin install superpowers@claude-plugins-official
/plugin marketplace add https://github.com/affaan-m/everything-claude-code
/plugin install everything-claude-code@everything-claude-code
```

### 3. Merge the config

Merge the relevant fields from `config/settings.example.json` into your `~/.claude/settings.json`.

If a specific project needs separate control, also use `config/project.settings.example.json`.

### 4. Restart Claude Code

Plugin activation and env changes depend on a restart.

## Security note

This repository contains **sanitized examples only**. Do not commit:

- API keys
- auth tokens
- your full personal `settings.json`
- private local paths or internal service URLs
