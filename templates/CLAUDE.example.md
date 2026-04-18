# Project CLAUDE Template

## Workflow ownership

- Superpowers owns default planning and execution flow
- ECC is used only for explicit capability calls
- Do not enable ECC heavy hooks by default

## Required default flow

For non-trivial work:

1. `superpowers:brainstorming`
2. `superpowers:writing-plans`
3. `superpowers:executing-plans` or `superpowers:subagent-driven-development`
4. `superpowers:test-driven-development`

## ECC usage rule

ECC can be used for:

- explicit skills
- explicit agents
- targeted commands

ECC should not silently replace the default planning / execution owner.

## Hook policy

Keep ECC hooks in capability mode unless the team explicitly approves restoring a specific hook id.
