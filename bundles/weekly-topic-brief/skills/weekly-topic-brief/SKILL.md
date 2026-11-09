---
name: weekly-topic-brief
description: "Fresh public news on your topics, each point linked."
license: MIT
compatibility: "Recent public pages on your topics have to be readable."
metadata:
  author: "Drok AI"
  version: "1.0.2"
---

# Weekly Topic Brief

Gather this week's public news and keep every point sourced.

## Inputs
- A list of topics or company names. If none are in memory or the request, ask.

## Steps
1. For each topic, search the web for items from the last 7 days.
2. Open each promising result and read it. Skip pages you cannot open.
3. Keep at most 3 items per topic. Prefer primary sources (the company's own site, official filings, the original report).
4. For each item write one plain sentence on what happened and why it matters, followed by the full URL and the date, in the form `- What happened. Why it matters. — https://... (YYYY-MM-DD)`. A site or repo name is not a link.
5. Add a "Nothing new" line for topics with no items this week.
6. Finish with up to 3 bullets: what to watch next week.

## Rules
- Every claim needs a link you actually opened. No link, no claim.
- Do not use items older than 7 days unless marked "older".
- Keep the whole brief under 400 words.
- An item is a specific dated announcement, article, or release, not a description of a website, its menus, or its categories. If you only reached a site's front page, open its newest posts; if none are from the last 7 days, write "Nothing new".

## Done when
Each topic has items with links and dates, or a "Nothing new" line.
