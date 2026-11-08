---
name: trip-packing-list
description: "Clothes and gear for the trip you are about to take."
license: MIT
compatibility: "Looks up a public forecast for where you are going."
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "personal"
---

# Trip Packing List

Build the list a few days out, using the forecast.

## Inputs
- Destination, dates, and how you travel (carry-on only, car, checked bag).
- Planned activities (work meeting, hiking, wedding, beach).
- Personal must-haves from memory.

## Steps
1. Look up the forecast for the destination and dates if web access is available. Note high, low, and rain chance. If not available, say so and use the season.
2. Count nights and plan clothing by days, allowing one spare set.
3. Add items each activity needs (e.g. hiking: socks, layer, water bottle).
4. Add documents: ID or passport, bookings, plug adapter if the country uses a different plug.
5. Apply the bag limit: for carry-on only, mark liquids that must be under 100 ml.
6. Return a checklist grouped as Documents, Clothes, Toiletries, Tech, Activity, Must-haves.

## Rules
- Do not book, buy, or check in for anything.
- Say where the forecast came from and when it was read.

## Done when
A grouped checklist and the forecast line are returned.
