# Follow-up Nudge

Quiet chats get a follow-up with a real point.

Midweek sales cleanup, Wednesday at 10:00.

`skills/follow-up-nudge/SKILL.md` is what to follow. Working days live in `memory.md`. Wednesday is noted in `routines.yaml`. No account is listed in `mcp.json`. Load `goose-recipe.yaml` for Goose.

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
Paste the quiet threads. Your mail stays unconnected.

You are free to copy this under MIT. Drok AI wrote it.
