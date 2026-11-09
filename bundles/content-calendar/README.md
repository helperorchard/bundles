# Content Calendar

Fortnight of posts drawn from your current goal.

Prefer every other Friday at 17:00. If your clock only does weekly, run each Friday and skip the in-between week.

Planning steps are in `skills/content-calendar/SKILL.md`. Voice and channels belong in `memory.md`. `routines.yaml` suggests the Friday run. `mcp.json` is unused here. Goose reads `goose-recipe.yaml`.

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
Nothing to plug in. Your goals and old posts are enough.

Shared under the MIT license. Drok AI is the author.
