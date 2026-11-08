# Newsletter Draft

Turns your rough notes and links from the week into a short, readable newsletter draft with a subject line.

Category: Marketing. Suggested schedule: every Thursday at 15:00.

Files: `skills/newsletter-draft/SKILL.md` (the skill), `memory.md` (facts to fill in and keep), `routines.yaml` (schedule), `mcp.json` (connectors), `goose-recipe.yaml`.

## Install

skills.sh CLI (Claude Code, Cursor, Codex, Goose, OpenClaw and more)
```
npx skills add helperorchard/bundles --skill newsletter-draft
```

Hermes Agent
```
hermes skills install helperorchard/bundles/bundles/newsletter-draft/skills/newsletter-draft
hermes cron create "0 15 * * 4" "Ask me for this week's notes and links, then run newsletter-draft." --skill newsletter-draft
```
Add the lines from `memory.md` to `~/.hermes/memories/MEMORY.md`.

Goose recipe and schedule
```
goose run --recipe goose-recipe.yaml
goose schedule add --schedule-id newsletter-draft --cron "0 0 15 * * 4" --recipe-source ./goose-recipe.yaml
```

Manual copy: put `skills/newsletter-draft` in `~/.agents/skills/` (Codex, Goose, Cursor) or `~/.claude/skills/` (Claude Code).

## Connectors
This bundle uses no connectors.

License: MIT. Original writing by Drok AI.
