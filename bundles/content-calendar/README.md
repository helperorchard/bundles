# Content Calendar

Plans the next two weeks of posts from your goals and past posts, with a date, channel, and hook for each.

Category: Marketing. Suggested schedule: every other Friday at 17:00 (set every Friday and skip alternate weeks if your tool lacks bi-weekly).

Files: `skills/content-calendar/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
