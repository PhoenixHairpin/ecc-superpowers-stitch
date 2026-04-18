# Apply the Integration

## 1. Install the plugins

```bash
/plugin install superpowers@claude-plugins-official
/plugin marketplace add https://github.com/affaan-m/everything-claude-code
/plugin install everything-claude-code@everything-claude-code
```

## 2. Merge the config

Merge these fields from `config/settings.example.json` into your `~/.claude/settings.json`:

- `extraKnownMarketplaces`
- `enabledPlugins`
- `env.ECC_HOOK_PROFILE`
- `env.ECC_DISABLED_HOOKS`

Do not overwrite your personal keys, model choice, theme, or permissions with the example file.

## 3. Restart Claude Code

Plugin activation and environment changes require a restart.

## 4. Verify the result

Success looks like this:

- Superpowers still owns the default workflow
- ECC is installed and available on demand
- ECC no longer auto-runs a full set of heavy PreToolUse / PostToolUse / Stop hooks

## 5. If you want to restore an ECC hook

Remove a specific id from `ECC_DISABLED_HOOKS`, then restart Claude Code.

Restore one at a time and watch for duplicate workflow behavior or extra noise.
