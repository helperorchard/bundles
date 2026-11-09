# Run logs

Raw output from real test runs, kept as proof for public "Verified" badges on the site.

## 2026-11-09

- Model: OpenRouter free models router (`openrouter/free`) only
- Harnesses: Hermes and Goose for each of the 24 helpers (safe sample inputs; nothing sent, posted, paid, or bought)
- Logs: `2026-11-09/<slug>-hermes.md` and `2026-11-09/<slug>-goose.md`
- Pass = helper completed its Done-when output. Rate limits retried with backoff; persistent free-router/network issues marked Blocked, not Fail. No fabricated logs.
- Notes:
  - `weekly-topic-brief` on free models needs real opened URLs with dates; both harnesses produced dated items (or honest "Nothing new") on this run.
  - `job-post-watch` Goose reported Cloudflare careers as "could not open" (JS-rendered); Hermes listed matching Cloudflare roles and marked the dead OpenAI Greenhouse board "could not open".

## 2026-11-08

- Model: OpenRouter free models router (`openrouter/free`)
- Harness: Hermes for every file except `weekly-meal-plan-goose.md`, which ran in Goose. Reruns follow bundle fixes.
- weekly-topic-brief did not reliably return source links on free models in that earlier set, so it was not counted as passing then.
