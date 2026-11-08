# Job Post Watch

Openings at chosen companies, only the new ones.

Weekdays at 07:00, before fresh posts get buried.

The hunt is described in `skills/job-post-watch/SKILL.md`. Pages, titles, and roles already seen go in `memory.md`. `routines.yaml` is the 07:00 weekday run. `mcp.json` adds no job-board login. `goose-recipe.yaml` covers Goose.

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
No job-board account. It only opens the careers links you listed.

The writing is Drok AI's and the license is MIT.
