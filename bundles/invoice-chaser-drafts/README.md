# Invoice Chaser Drafts

Writes polite, firm payment reminder drafts for overdue invoices, stepped by how late each one is. Never sends.

Category: Sales. Suggested schedule: every Tuesday at 09:00.

Files: `skills/invoice-chaser-drafts/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill invoice-chaser-drafts
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/invoice-chaser-drafts/skills/invoice-chaser-drafts
hermes cron create "0 9 * * 2" "Ask me for the current unpaid invoice list, then run invoice-chaser-drafts." --skill invoice-chaser-drafts
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id invoice-chaser-drafts --cron "0 0 9 * * 2" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/invoice-chaser-drafts` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
