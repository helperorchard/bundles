---
name: weekly-meal-plan
description: "Plans dinners for the week around your diet, time limits, and what is already in the fridge, plus one shopping list."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "personal"
---

# Weekly Meal Plan

Use this on the weekend to plan the week's dinners.

## Inputs
- Number of people, diet needs, and dislikes (from memory).
- What is already in the fridge and pantry.
- Busy nights when cooking must take under 20 minutes.

## Steps
1. Plan 5 dinners (or the number asked). Use up the fridge items that spoil soonest in the first two nights.
2. Put quick meals on the busy nights.
3. Reuse ingredients across meals so half a bunch of something is not wasted, and say where.
4. For each dinner give: name, rough time, and the main ingredients. Not full recipes unless asked.
5. Build one shopping list grouped by store section, leaving out what the user already has.

## Rules
- Respect every allergy in memory; when unsure if an item is safe, leave it out and say why.
- Do not order groceries or fill any cart.

## Done when
The dinner plan and the grouped shopping list are returned.
