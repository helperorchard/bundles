# Invoice Chaser Drafts

Polite chase notes you send only when ready.

Tuesday at 09:00, with the unpaid list in front of you.

Reminder writing is `skills/invoice-chaser-drafts/SKILL.md`. Terms and payment details belong in `memory.md`. Tuesday is in `routines.yaml`. `mcp.json` has no mail account. Goose uses `goose-recipe.yaml`.

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
No email connection. Copy the reminder into your own mail.

Take it under MIT, with credit to Drok AI for the words.
