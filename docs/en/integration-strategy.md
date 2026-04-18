# ECC + Superpowers Integration Strategy

## Control split

### Primary workflow: Superpowers

Superpowers is responsible for:

- brainstorming
- design approval
- writing-plans
- executing-plans / subagent-driven-development
- test-driven-development
- requesting-code-review

### Capability layer: ECC

ECC is responsible for:

- extra commands / skills / agents
- explicit workflow enhancements when you ask for them
- not owning the default workflow
- not owning heavy hooks

## Owner matrix

| Area | Owner |
|---|---|
| Requirements clarification | Superpowers |
| Design approval | Superpowers |
| Planning breakdown | Superpowers |
| Execution flow | Superpowers |
| TDD discipline | Superpowers |
| Extra capability calls | ECC |
| Optional toolbox | ECC |
| Default heavy hooks | Disabled for ECC |

## Why disable ECC heavy hooks

ECC is powerful because of its breadth and automation, but its PreToolUse / PostToolUse / Stop surface is large.
When stacked with Superpowers' strong workflow control, the common outcome is:

- duplicate planning
- duplicate review
- duplicate verification
- additional latency
- more context noise

The stable approach is:

- keep the ECC plugin installed
- set `ECC_HOOK_PROFILE` to `minimal`
- disable heavy hook ids with `ECC_DISABLED_HOOKS`

## Non-conflict rules

1. Only one workflow owner: Superpowers
2. ECC is explicit-only, not the default controller
3. Do not let both systems make decisions on the same event/matcher class
4. Do not use deprecated generic Superpowers commands
5. Keep a single source of truth for specs and plans

## Future expansion

If you later want to restore part of ECC, remove hook ids from `ECC_DISABLED_HOOKS` one at a time instead of turning everything back on at once.
