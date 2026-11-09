# Content Calendar

Fourteen days of posts, each with a day and a hook. Every other Friday at 17:00 fits. If your tool only understands every Friday, run it then and skip the quiet week.

Channels and voice go in `memory.md`. The Friday 17:00 slot is `routines.yaml`. Planning steps are `skills/content-calendar/SKILL.md`. Take `goose-recipe.yaml` into Goose. `mcp.json` has nothing to sign into.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill content-calendar
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/content-calendar/skills/content-calendar
hermes cron create "0 17 * * 5" "Run content-calendar for the next two weeks using my goal and channels in memory." --skill content-calendar
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id content-calendar --cron "0 0 17 * * 5" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/content-calendar` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
The plan stays on the page. Publishing is left to you.

License: MIT. Original writing by Drok AI.
