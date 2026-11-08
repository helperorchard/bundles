---
name: competitor-price-watch
description: "Which competitor prices moved since the last check."
license: MIT
compatibility: "Needs web access."
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "marketing"
---

# Competitor Price Watch

See which plans moved without opening every tab.

## Inputs
- A list of competitor pricing page URLs (from memory or the request).
- The last saved prices, if any, from memory.

## Steps
1. Open each pricing URL. If it will not load, write "could not open" and move on.
2. For each plan or product on the page, record: plan name, price, billing period, and the main limit (seats, units, size).
3. Compare with the last saved prices. Mark each line NEW, CHANGED (old to new), REMOVED, or SAME.
4. Report a table per competitor with CHANGED and NEW lines first, then a one-line summary like "2 of 5 competitors changed prices".
5. Give the user the updated price list to save back into memory.

## Rules
- Only read public pages. Never log in, start a trial, or fill in forms.
- Copy prices exactly as shown, with currency. If a price says "contact us", record that, do not estimate.
- If a page shows different prices by region, note which one you saw.

## Done when
Each competitor has a table and the updated price list is ready to save.
