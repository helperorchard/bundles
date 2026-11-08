# Follow-up Nudge

Each quiet thread gets a nudge that adds something new. Wednesday at 10:00 is the sweep already suggested.

Work days and the nudge limit go in `memory.md`. Wednesday 10:00 is `routines.yaml`. Wording rules are `skills/follow-up-nudge/SKILL.md`. `goose-recipe.yaml` carries the same job for Goose. `mcp.json` does not open your inbox.

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
Threads are pasted by you, and the inbox is left alone.

License: MIT. Original writing by Drok AI.
