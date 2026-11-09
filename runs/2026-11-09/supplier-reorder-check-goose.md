
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_25 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: supplier-reorder-check

# Loaded Skill: supplier-reorder-check (skill)

Compares your stock counts with reorder points and drafts the purchase list per supplier. Does not place orders.

## Content

# Supplier Reorder Check

Use this for a small shop, kitchen, or studio that counts stock by hand.

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
**Supplier → Order Items (draft messages)**  

- **Roastery Co**  
  - Coffee beans – **10 kg**  
  - *Draft message:* “Please order 10 kg of Coffee beans.”

- **Paper Goods Inc**  
  - Cups 12 oz – **500**  
  - Napkins – **20 packs**  
  - *Draft message:* “Please order 500 Cups 12 oz and 20 packs of Napkins.”

- **Dairy Depot** – no ORDER items (stock is above the reorder point and not within the 20 % LOW threshold).

---

**LOW items** (within 20 % above reorder point)  
- *None.*

---

**Needs a reorder point**  
- Sugar packets (no reorder point defined).

Loading recipe: Supplier Reorder Check
Description: Compares your stock counts with reorder points and drafts the purchase list per supplier. Does not place orders.

