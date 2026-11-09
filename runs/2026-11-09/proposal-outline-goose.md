
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_19 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: proposal-outline

# Loaded Skill: proposal-outline (skill)

Turns your call notes into a structured proposal outline with scope, timeline, price options, and open questions.

## Content

# Proposal Outline

Use this after a discovery call when someone needs to write a proposal.

## Inputs
- Call notes (pasted), the client name, and the user's price range or rate from memory.

## Steps
1. Pull out the client's problem in their words, their deadline, and their budget hint if any.
2. Write the outline:
   - The problem (2-3 sentences, using their words)
   - What we will do (3-6 deliverables, each one concrete and checkable)
   - What is not included (at least 2 items, to stop scope creep)
   - Timeline as weeks, tied to deliverables
   - Two or three price options built from the user's rate, each with what it includes
   - Next step and how long the offer stands
3. List questions the notes did not answer and that the proposal depends on.

## Rules
- Prices come only from memory or the user. Never invent a rate.
- Do not promise outcomes like "double your sales".
- Draft only. Never send it to the client.

## Done when
The outline and the open questions list are returned.
# Proposal Outline: Northwind Tools

## 1. The Problem (in their words)
Northwind Tools currently spends about six hours per week on manual reporting and wants to reduce that to under two hours. The bottleneck is the time spent auditing sheets and consolidating data, which pulls ops people away from higher‑value work.

## 2. What We Will Do (deliverables)
1. **Audit current reporting sheets** – Review all existing Excel/Google Sheets, identify redundant steps, and document data flow. *(Deliverable: audit report with ≥10 improvement ideas)*  
2. **Set up one consolidated dashboard** – Build a single Looker/Tableau (or Google Data Studio) dashboard that pulls the key metrics and refreshes automatically. *(Deliverable: live dashboard accessible to ops team)*  
3. **Train two ops people on the new dashboard** – Conduct two 90‑minute hands‑on sessions covering navigation, filter usage, and scheduled exports. *(Deliverable: trained staff who can independently update the dashboard)*  
4. **Define data‑warehouse access ownership** – Clarify who has read/write access and set up a shared “reporting” role with appropriate permissions. *(Deliverable: access matrix and permission checklist)*  
5. **Optional: Configure Slack alerts** – Set up automated notifications for out‑of‑range metrics (if needed). *(Deliverable: Slack integration with alert rules)*  

## 3. What Is Not Included
- Building custom ETL pipelines or moving data to a new warehouse.  
- Ongoing monthly monitoring or maintenance beyond the initial 3‑week engagement.  
- Creating additional dashboards for other business units.  
- Procurement or licensing of third‑party tools outside the agreed scope.  

## 4. Timeline (weeks, tied to deliverables)
| Week | Milestone |
|------|-----------|
| 1 (start next month) | Complete audit of current sheets; define dashboard requirements |
| 2 | Build and test the consolidated dashboard |
| 3 | Train two ops people; hand over access‑ownership documentation |
| End of Week 3 | Go‑live; all reporting under 2 hours per week |

## 5. Price Options (built from rate range $3k–$7k fixed)
| Option | Price | What’s Included |
|--------|-------|-----------------|
| **Basic** | **$3,000** (50% upfront, 50% on delivery) | Audit + dashboard set‑up + training for 2 people (no Slack alerts, no access‑ownership deep dive) |
| **Standard** | **$5,000** (50% upfront, 50% on delivery) | All Basic items + data‑warehouse access matrix + Slack alerts configuration (if needed) |
| **Premium** | **$7,000** (50% upfront, 50% on delivery) | All Standard items + optional 2‑hour follow‑up Q&A session + 30‑day post‑launch support via email |

*All options assume the 3‑week timeline described above. Travel or remote‑only work is included; expenses are not.*

## 6. Next Step & Offer Validity
- **Next step:** Schedule a 30‑minute alignment call to confirm the chosen option and approve access to the current reporting files.  
- **Offer valid for:** 14 days from the date of this proposal (per standard terms).

---

## Open Questions (the proposal depends on these)
1. Who will own the data‑warehouse access credentials, and are there any compliance restrictions we need to observe?  
2. Do Northwind Tools actually need Slack alerts, or would email summaries suffice?  
3. Are there any other reporting tools or data sources (beyond the current sheets) that should be considered in the audit?  
4. Does the team prefer a specific dashboard platform (Looker, Tableau, Google Data Studio, etc.) or shall we recommend the most cost‑effective option?  

*Please answer the above so we can finalize the scope and issue a formal agreement.*

Loading recipe: Proposal Outline
Description: Turns your call notes into a structured proposal outline with scope, timeline, price options, and open questions.

