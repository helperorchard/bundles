# Follow-up Nudge

Looks at your list of open conversations and drafts a short, useful follow-up for each one that has gone quiet. Drafts only.

Category: Sales. Suggested schedule: every Wednesday at 10:00.

Files: `skills/follow-up-nudge/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill follow-up-nudge
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/follow-up-nudge/skills/follow-up-nudge
hermes cron create "0 10 * * 3" "Ask me for my open threads, then run follow-up-nudge." --skill follow-up-nudge
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id follow-up-nudge --cron "0 0 10 * * 3" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/follow-up-nudge` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
