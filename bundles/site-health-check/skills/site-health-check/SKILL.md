---
name: site-health-check
description: "Catches pages that are down or thin in search."
license: MIT
compatibility: "Listed pages need to load when the check runs."
metadata:
  author: "Drok AI"
  version: "1.0.0"
---

# Site Health Check

Say which saved pages are down and which look thin.

## Inputs
- One or more page URLs. If none are given, ask for them.

## Steps
1. For each URL, request the page and note the status code and how long it took.
2. Mark the page DOWN if the status is not 2xx or 3xx, or it takes longer than 10 seconds.
3. For pages that load, check the HTML for:
   - a `<title>` between 10 and 60 characters
   - a meta description between 50 and 160 characters
   - exactly one `<h1>`
   - a canonical link
   - `noindex` in a robots meta tag (flag it if present)
4. Collect up to 20 links on the page and request each one. List any that return 4xx or 5xx.
5. Report a short table: URL, status, time, issues found. Put DOWN pages first.

## Rules
- Read only. Never submit forms or log in.
- Say "not checked" instead of guessing when a request fails for a network reason.

## Done when
Every URL has a status line and either "no issues" or a list of issues.
