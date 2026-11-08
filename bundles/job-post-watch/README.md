# Job Post Watch

Checks the careers pages you list for new roles that match your title and location, and reports only the new ones.

Category: Personal. Suggested schedule: every weekday at 07:00.

Files: `skills/job-post-watch/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

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
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
