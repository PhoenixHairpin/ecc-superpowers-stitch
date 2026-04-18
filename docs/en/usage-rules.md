# Usage Rules

## Default working posture

### 1. Design first, then plan, then execute

- `superpowers:brainstorming`
- `superpowers:writing-plans`
- `superpowers:executing-plans` or `superpowers:subagent-driven-development`
- `superpowers:test-driven-development`

### 2. ECC only enters when explicitly needed

Good ECC use cases:

- targeted skill / agent help
- extra toolbox capability
- specialized workflows on demand

Bad ECC default use cases:

- taking over the whole development flow
- wrapping every response in a second control layer
- redefining the main design / planning / execution path

## Daily decision rule

If an ECC feature automatically adds another layer around `Bash`, `Edit`, `Write`, or `Stop`, it is usually not a good default-on candidate.

If it simply gives you an extra capability you invoke explicitly, it is usually a good ECC keep.

## Minimal-conflict rules

- planning belongs to Superpowers
- the default review rhythm belongs to Superpowers
- ECC strengthens the system but does not take ownership
- restore ECC hooks one by one only
