
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_46 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: job-post-watch

# Loaded Skill: job-post-watch (skill)

Checks the careers pages you list for new roles that match your title and location, and reports only the new ones.

## Content

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

  ────────────────────────────────────────
  ▸ load_skill
    name: web-search

# Loaded Skill: web-search (builtin skill)

Search the web and extract page content using DuckDuckGo (no API key required), Tavily, or SearXNG. Use whenever the task needs current information, facts not in training data, or content from a specific URL.

## Content

## Requirements

- `uv` must be installed (`curl -LsSf https://astral.sh/uv/install.sh | sh`)
- No API key required for the default DuckDuckGo path

## Search

**Default — DuckDuckGo (no API key):**
```bash
uvx ddgs text -q "your query here" -m 5
```

**Tavily (richer results, requires `TAVILY_API_KEY`):**
```bash
uvx --from tavily-python python -c "
import os
from tavily import TavilyClient
r = TavilyClient(os.environ['TAVILY_API_KEY']).search('your query here', max_results=5)
for res in r['results']:
    print(res['url'])
    print(res['content'])
    print()
"
```

**SearXNG (self-hosted, requires `SEARXNG_URL`):**
```bash
curl -sG --data-urlencode "q=your query here" --data "format=json" "${SEARXNG_URL}/search" | python3 -c "
import json, sys
data = json.load(sys.stdin)
for r in data.get('results', [])[:5]:
    print(r['url'])
    print(r.get('content',''))
    print()
"
```

Pick the first available: Tavily if `TAVILY_API_KEY` is set, SearXNG if `SEARXNG_URL` is set, otherwise DuckDuckGo.

## Extract page content

```bash
url="https://example.com"
tmpfile=$(mktemp /tmp/page-XXXXXX)
curl -sL --max-time 15 -A "Mozilla/5.0" "$url" | uvx html2text --ignore-links > "$tmpfile" 2>/dev/null
wc -c "$tmpfile"
head -c 15000 "$tmpfile"
```

If the page is larger than 15 000 characters, show both head and tail so the user can decide whether to read the full file:
```bash
echo "--- HEAD ---"
head -c 7500 "$tmpfile"
echo ""
echo "--- TAIL ---"
tail -c 7500 "$tmpfile"
echo ""
echo "(Full content saved to $tmpfile)"
```

## Rules

- Always quote search queries to avoid shell word-splitting.
- Respect robots.txt for scraping; do not hammer a host with repeated requests.
- Never send authentication cookies or session tokens to external URLs.
- If a page returns a login wall or CAPTCHA, report the URL and stop; do not attempt to bypass it.




  ────────────────────────────────────────
  ▸ shell
    command: tmpfile=$(mktemp /tmp/cf-careers-XXXXXX); curl -sL --max-time 20 -A "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36" "https://www.cloudflare.com/careers/jobs/" -o "$tmpfile" 2>/dev/null; echo "SIZE: $(wc -c < "$tmpfile")"; echo "$tmpfile"

SIZE: 164018
/tmp/cf-careers-lXdXJP
  ────────────────────────────────────────
  ▸ shell
    command: python3 - <<'EOF'
import re, html
data = open('/tmp/cf-careers-lXdXJP', 'rb').read().decode('utf-8', 'ignore')
# strip scripts/styles
data = re.sub(r'(?is)<(script|style).*?</\1>', '', data)
text = re.sub(r'(?s)<[^>]+>', '\n', data)
text = html.unescape(text)
lines = [l.strip() for l in text.split('\n') if l.strip()]
print(len(lines))
for l in lines[:200]:
    print(l)
EOF

76
Careers at Cloudflare — Open Positions | Cloudflare
Products
Solutions
Resources
Pricing
Login
Dashboard
Contact sales
Start building
Dashboard
Login
Help Us Build a Better Internet
At Cloudflare, we want you to have the career of your dreams. We invest in and support curious, mission-minded people who are committed to solving the Internet's toughest challenges.
Cloudflare has historically been an in-office, yet globally distributed, company. We are now evolving into a hybrid model that is even more distributed, with a commitment to maintaining an equitable and inclusive workplace for all.
Open roles
Loading roles…
All departments
All locations
Filters & sort
Role
Team and location
Date posted
Getting started
Plans
Contact sales
Partners
Find a partner
Startups
Under attack?
Domain name search
Company
About
Careers
Investors
Press
Press kit
Global network
Public interest
Project Galileo
Athenian Project
Cloudflare for Campaigns
Project Fairshot
Impact
Compliance
Compliance resources
Trust Hub
Data Protection
Responsible AI
Transparency report
Report abuse
Resources
App innovation report
Cloudflare Radar
Case studies
Status
Support
Events
Blog
Developers
Documentation
Learning center
Community
Solutions
SSE and SASE platform
Start Building
Log In
© 2026 Cloudflare, Inc.
Privacy policy
|
Report security issues
|
Terms of use
|
Trademark
|
Your privacy choices
  ────────────────────────────────────────
  ▸ shell
    command: python3 - <<'EOF'
import re
data = open('/tmp/cf-careers-lXdXJP', 'rb').read().decode('utf-8', 'ignore')
# find application/json or data-* blocks
m = re.findall(r'(?is)<script[^>]*type=["\']application/json["\'][^>]*>(.*?)</script>', data)
print('JSON blocks:', len(m))
for j in m[:5]:
    print('---', len(j), '---')
    print(j[:400])
    print()
# Also find any mention of location keywords
for kw in ['San Francisco','Remote','Software Engineer','Developer Advocate','posted']:
    hits = [i for i in range(len(data)) if data[i:i+len(kw)].lower()==kw.lower()]
    if hits: print(kw, hits[:2])
EOF

JSON blocks: 0
posted [107382, 107415]could not open

Loading recipe: Job Post Watch
Description: Checks the careers pages you list for new roles that match your title and location, and reports only the new ones.

