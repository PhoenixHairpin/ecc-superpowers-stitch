# Customize This Template

## What you should usually keep unchanged

### 1. The stable core

Recommended defaults:

- Superpowers remains the primary workflow owner
- ECC remains capability-only by default
- `ECC_HOOK_PROFILE` stays `minimal`
- ECC heavy hooks stay disabled by default

### 2. What you can tune safely

#### A. Restore one ECC hook

If you truly need a specific ECC behavior:

- remove one hook id from `ECC_DISABLED_HOOKS`
- restart Claude Code
- watch for duplicated workflow, repeated reminders, or extra noise

Restore one at a time.

#### B. Project-level control

If you do not want this to affect every project, move the rule set into project-level `.claude/settings.json`.

Use these references:

- `config/project.settings.example.json`
- `templates/CLAUDE.example.md`

#### C. Team-facing guidance

You can add project-specific rules such as:

- when brainstorming is mandatory
- which tasks can skip straight to implementation
- which ECC capabilities are approved for explicit use

## What you should avoid

- letting ECC and Superpowers both control `Bash|Edit|Write|Stop` by default
- re-enabling ECC's full automatic workflow surface
- using deprecated generic Superpowers commands
- maintaining two parallel plan/spec systems

## Recommended evolution path

### Phase 1: Stability

- Superpowers owns workflow
- ECC runs in capability mode
- ECC hooks are mostly off

### Phase 2: Selective restore

- observe what capability is missing
- restore hook ids one at a time
- preserve the single-owner rule

### Phase 3: Team standardization

- write approved restore items into project CLAUDE.md
- turn them into a shared team rule
