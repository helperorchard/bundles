# Invoice Chaser Drafts

Reminder wording that matches how late each invoice is. Tuesday at 9:00 is a good pass over what is overdue.

Payment terms and the late-fee rule live in `memory.md`. Tuesday 9:00 is `routines.yaml`. Tone steps are `skills/invoice-chaser-drafts/SKILL.md`. Goose keeps `goose-recipe.yaml`. `mcp.json` will not open your mail.

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
Invoice details are pasted, and mail is never opened.

License: MIT. Original writing by Drok AI.
