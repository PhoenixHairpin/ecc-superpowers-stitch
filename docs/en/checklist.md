# Fork Checklist

## Do these first after forking

- [ ] update the repository description
- [ ] choose private or public visibility
- [ ] read `docs/en/integration-strategy.md`
- [ ] read `docs/en/customize.md`
- [ ] decide between global and project-level settings
- [ ] merge `config/settings.example.json`
- [ ] restart Claude Code

## Verify it works

- [ ] Superpowers still owns the default workflow
- [ ] ECC is enabled and available explicitly
- [ ] ECC no longer auto-runs heavy Pre/Post/Stop hooks by default
- [ ] there is no duplicate planning or duplicate review flow

## If you want to extend it later

- [ ] add your own CLAUDE template
- [ ] add team-specific working rules
- [ ] record which ECC hooks are safe to restore
