
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_34 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: weekly-meal-plan

# Loaded Skill: weekly-meal-plan (skill)

Plans dinners for the week around your diet, time limits, and what is already in the fridge, plus one shopping list.

## Content

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
**Dinner Plan (Mon–Fri)**

| Night | Dinner | Time | Main Ingredients |
|-------|--------|------|------------------|
| Mon | Spinach & Sweet Potato Egg Scramble | ~20 min | Spinach, sweet potatoes, eggs, feta |
| Tue* | Chickpea Coconut Curry over Rice | ~15 min | Chickpeas, coconut milk, rice, spinach |
| Wed | Sweet Potato & Chickpea Power Bowl | ~30 min | Sweet potatoes, chickpeas, spinach, feta, rice |
| Thu* | Egg Fried Rice with Spinach | ~15 min | Eggs, rice, spinach |
| Fri | Baked Sweet Potatoes with Chickpeas & Feta | ~35 min | Sweet potatoes, chickpeas, feta |

*\*Busy night — under 20 minutes.*

**Ingredient reuse:** Spinach used Mon–Thu; sweet potatoes Mon/Wed/Fri; chickpeas Tue/Wed/Fri; rice Tue/Wed/Thu; eggs Mon/Thu; feta Mon/Wed/Fri; coconut milk Tue.

**Shopping List** (excludes items you already have)

**Produce:** onion, garlic, lemon, fresh herbs (cilantro or parsley)

**Pantry / Spices:** cooking oil, soy sauce, curry powder or garam masala, salt & pepper

**Dairy / Refrigerated:** butter (optional, if not stocked)

All vegetarian, peanut-free, and mushroom-free. No groceries ordered.

Loading recipe: Weekly Meal Plan
Description: Plans dinners for the week around your diet, time limits, and what is already in the fridge, plus one shopping list.

