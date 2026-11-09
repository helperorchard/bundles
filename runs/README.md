# Run logs

Raw output from real test runs, kept as proof for public "Verified" badges on the site.

## 2026-11-09

- Model: OpenRouter free models router (`openrouter/free`)
- Harnesses: Hermes and Goose for each helper (safe sample inputs only; nothing sent, posted, paid, or bought)
- Logs: `2026-11-09/<slug>-hermes.md` and `2026-11-09/<slug>-goose.md`
- Pass = helper completed its Done-when output. Rate limits marked Blocked, not Fail. No fabricated logs.

## 2026-11-08

- Model: OpenRouter free models router (`openrouter/free`)
- Harness: Hermes for every file except `weekly-meal-plan-goose.md`, which ran in Goose. Reruns follow bundle fixes.
- weekly-topic-brief did not reliably return source links on free models, so it is not counted as passing.
