
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_14 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: lead-list-cleanup

# Loaded Skill: lead-list-cleanup (skill)

Tidies a messy lead list you paste in: merges duplicates, fixes name and company formats, and flags rows missing key fields.

## Content

# Lead List Cleanup

Use this when someone has a lead list from a spreadsheet, event, or form export that is messy.

## Inputs
- The list as pasted rows or CSV text. Columns can be in any order.

## Steps
1. Identify the columns: name, email, company, role, source, notes. Ask only if you cannot tell.
2. Normalise: trim spaces, capitalise names, lowercase emails, remove "Inc."-style noise only for matching (keep it in output).
3. Find duplicates by same email, or same name plus same company. Merge them, keeping the newest non-empty value per field and joining notes.
4. Flag rows with no email, an email that is not shaped like name@domain, or a free-mail address when the list is meant to be business leads.
5. Return: the clean list as CSV, then counts (rows in, rows out, merged, flagged), then the flagged rows with the reason.

## Rules
- Do not look people up or add data that was not in the list.
- Do not delete flagged rows; mark them.
- Do not email or add anyone to any tool.

## Done when
The clean CSV, the counts, and the flagged rows are returned.


# Lead List Cleanup

## Clean CSV

```csv
name,email,company,role,source
Maya Chen,maya@northwind.example,Northwind,Ops Lead,linkedin
,jordan@beta.example,Beta LLC,,referral
Sam Okonkwo,sam@,Acme Co,Founder,twitter
Lin Park,lin@example.com,Example Cafe,Owner,walk-in
```

## Counts

| Metric | Value |
|---|---|
| Rows in | 5 |
| Rows out | 4 |
| Merged | 1 |
| Flagged | 3 |

## Merged

- **Maya Chen** — rows 1 & 2 matched on same email (`maya@northwind.example`). Kept newest non-empty value per field: company **Northwind** (row 2), role **Ops Lead** (row 2), source **linkedin** (row 2). Row 1's "Northwind Tools" / "Head of Ops" / "conf-booth" were superseded.

## Flagged rows

| Row | Issue |
|---|---|
| Jordan (row 3) | **Missing name** — no name provided (role also blank). Email `jordan@beta.example` is valid, so kept. |
| Sam Okonkwo (row 4) | **Invalid email** — `sam@` is not shaped like `name@domain`. |
| Lin Park (row 5) | **Non-business email domain** — `lin@example.com` uses the reserved placeholder domain `example.com`, not a real business domain. Not a free-mail provider (gmail/yahoo), but not a company domain either — verify before outreach. |

Loading recipe: Lead List Cleanup
Description: Tidies a messy lead list you paste in: merges duplicates, fixes name and company formats, and flags rows missing key fields.

