# Job Post Watch

Weekday look at job posts that fit your titles. Mornings at 7:00, before the workday starts.

Careers links, titles, and places go in `memory.md`. Weekday 7:00 is `routines.yaml`. The watch itself is `skills/job-post-watch/SKILL.md`. Goose runs `goose-recipe.yaml`. `mcp.json` does not log into a job board.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill job-post-watch
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/job-post-watch/skills/job-post-watch
hermes cron create "0 7 * * 1-5" "Run job-post-watch on the careers pages in memory and show me only new matches." --skill job-post-watch
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id job-post-watch --cron "0 0 7 * * 1-5" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/job-post-watch` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
Only the careers links you listed get opened.

License: MIT. Original writing by Drok AI.
