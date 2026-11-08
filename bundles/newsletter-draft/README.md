# Newsletter Draft

One readable letter from the notes and links you saved. Thursday at 15:00 leaves time to send it yourself.

`memory.md` remembers the letter's name and sign-off. Thursday 15:00 is `routines.yaml`. Drafting lives in `skills/newsletter-draft/SKILL.md`. Goose reads `goose-recipe.yaml`. `mcp.json` is not an email login.

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
Copy the letter out yourself when you are happy with it.

License: MIT. Original writing by Drok AI.
