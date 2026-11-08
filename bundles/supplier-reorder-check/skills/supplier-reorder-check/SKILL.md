---
name: supplier-reorder-check
description: "Low stock becomes a purchase list per supplier."
license: MIT
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "operations"
---

# Supplier Reorder Check

You still place the order after reading the list.

## Inputs
- Current counts: item and quantity on hand.
- From memory: each item's reorder point, order quantity, and supplier.

## Steps
1. For each item, compare on-hand with its reorder point. Mark ORDER if at or below, LOW if within 20% above, OK otherwise.
2. For items with no reorder point in memory, list them under "Needs a reorder point".
3. Group ORDER items by supplier with the order quantity from memory.
4. For each supplier, draft a short order message listing items and quantities.
5. Show LOW items separately so the user can decide.

## Rules
- Never place an order, send a message, or open a supplier site to buy.
- Use the user's units exactly (cases, kg, packs). Do not convert unless asked.

## Done when
There is an order list per supplier with draft messages, plus LOW and missing-point lists.
