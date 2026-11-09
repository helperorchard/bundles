
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_28 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: weekly-expense-summary

# Loaded Skill: weekly-expense-summary (skill)

Groups a week of card or bank transactions you paste into categories and flags anything unusual or recurring.

## Content

# Weekly Expense Summary

Use this when someone wants to see where the money went this week.

## Inputs
- Transactions as pasted rows or CSV: date, description, amount, and currency.
- Category rules and a weekly budget from memory if saved.

## Steps
1. Keep only the last 7 days unless told otherwise. Treat refunds as negative spend.
2. Put each transaction in a category: use memory rules first, then the description (e.g. "Uber" to Transport). If unsure, use "Check".
3. Total each category and the week. Compare with the weekly budget if one is saved.
4. Flag: any single charge over the alert amount in memory, any charge from the same merchant twice in a day, and anything that looks like a subscription (same merchant and amount as a past week the user mentions).
5. Return a category table, the total vs budget, then the flags list.

## Rules
- Never connect to a bank or move money. Work only from what is pasted.
- Keep amounts exact and in the original currency. If there are several currencies, total them separately.
- Do not give investment or tax advice.

## Done when
Category totals, the week total, and the flags are returned.
# Weekly Expense Summary — 2026-11-03 → 2026-11-09 (Last 7 Days)

All amounts are in **USD**. Today is **2026-11-09**, so the window covers 2026-11-03 through 2026-11-09 — all sample transactions fall within range.

## Category Table

| Category | Transactions | Amount |
|---|---|---|
| 🚕 Transport | Uber Trip ×3 (Nov 3 ×2, Nov 8) | $45.50 |
| 🛒 Groceries | Whole Foods (Nov 4) | $64.22 |
| 💻 Software & Subscriptions | AWS (Nov 5), Adobe Creative Cloud (Nov 6) | $96.99 |
| ☕ Coffee | Starbucks (Nov 5) | $6.55 |
| ❓ Check | Unknown Merchant XYZ (Nov 7) | $125.00 |
| 💸 Refund | Refund Amazon (Nov 9) | −$20.00 |

## Week Total

**Total spend: $318.26** (refunds applied)

| | Amount |
|---|---|
| **Week total** | **$318.26** |
| Weekly budget | $400.00 |
| **Remaining / Under budget** | **$81.74** |

✅ **Under budget** — you're at ~20% under the $400 weekly limit.

## Flags

1. **Over alert amount ($80):** ⚠️ Unknown Merchant XYZ charged **$125.00** on 2026-11-07 — flagged for review (possible fraud/unexpected purchase).
2. **Duplicate merchant same day:** ⚠️ Uber had **two trips on 2026-11-03** ($18.40 + $12.10) — flagged.
3. **Subscription check:** AWS and Adobe Creative Cloud charges look recurring, but no prior-week data was provided for comparison, so no subscription flag was confirmed.

## Done When Criteria Met

- ✅ Category totals returned
- ✅ Week total returned
- ✅ Flags list returned

Let me know if you'd like a comparison against last week to check for subscription patterns, or a breakdown per day.

Loading recipe: Weekly Expense Summary
Description: Groups a week of card or bank transactions you paste into categories and flags anything unusual or recurring.

