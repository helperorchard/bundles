---
name: job-post-watch
description: "Checks the careers pages you list for new roles that match your title and location, and reports only the new ones."
license: MIT
compatibility: "Needs web access."
metadata:
  author: "Drok AI"
  version: "1.0.0"
  category: "personal"
---

# Job Post Watch

Use this when someone is job hunting and wants to know about new openings at companies they like.

## Inputs
- Careers page URLs (from memory).
- Target titles, location or remote, and deal-breakers (from memory).
- Roles already seen last time (from memory).

## Steps
1. Open each careers page. If it lists jobs through a job board link, follow that one link.
2. List every role with title, location, and link.
3. Keep only roles whose title matches a target title or a close variant, and whose location fits.
4. Drop roles already in the seen list. Mark the rest NEW.
5. For each NEW role, open the posting and note: seniority, salary range if stated, and any deal-breaker found.
6. Return the NEW roles, then the updated seen list to save back to memory.

## Rules
- Read only. Never apply, sign up, or upload a CV.
- If a page will not load or needs a login, say so; do not guess its roles.

## Done when
NEW roles are listed with links, and the seen list is ready to save.
