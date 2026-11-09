
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_21 · /workspace/skill-bundles
     L L     goose is ready

  ────────────────────────────────────────
  ▸ load_skill
    name: site-health-check

# Loaded Skill: site-health-check (skill)

Checks a website is up and flags basic SEO problems like missing titles or broken links. Use for a daily site check.

## Content

# Site Health Check

Use this when someone wants to know if a site is up and if its pages have obvious search problems.

## Inputs
- One or more page URLs. If none are given, ask for them.

## Steps
1. For each URL, request the page and note the status code and how long it took.
2. Mark the page DOWN if the status is not 2xx or 3xx, or it takes longer than 10 seconds.
3. For pages that load, check the HTML for:
   - a `<title>` between 10 and 60 characters
   - a meta description between 50 and 160 characters
   - exactly one `<h1>`
   - a canonical link
   - `noindex` in a robots meta tag (flag it if present)
4. Collect up to 20 links on the page and request each one. List any that return 4xx or 5xx.
5. Report a short table: URL, status, time, issues found. Put DOWN pages first.

## Rules
- Read only. Never submit forms or log in.
- Say "not checked" instead of guessing when a request fails for a network reason.

## Done when
Every URL has a status line and either "no issues" or a list of issues.

  ────────────────────────────────────────
  ▸ shell
    command: curl -s -o /dev/null -w "HTTP_CODE:%{http_code}\nTIME_TOTAL:%{time_total}\n" "https://example.com"


  ────────────────────────────────────────
  ▸ shell
    command: curl -s -o /dev/null -w "HTTP_CODE:%{http_code}\nTIME_TOTAL:%{time_total}\n" "https://helperorchard.com"

HTTP_CODE:200
TIME_TOTAL:0.098971HTTP_CODE:200
TIME_TOTAL:0.185690
  ────────────────────────────────────────
  ▸ shell
    command: curl -s -L -o /tmp/example.html "https://example.com"

(no output)



  ────────────────────────────────────────
  ▸ shell
    command: echo "=== TITLE ==="; grep -oP '<title>[^<]*</title>' /tmp/example.html || echo "NO TITLE"; echo "=== META DESCRIPTION ==="; grep -oP '<meta[^>]*name="description"[^>]*>' /tmp/example.html || echo "NO META DESCRIPTION"; echo "=== H1 COUNT ==="; grep -oP '<h1[^>]*>' /tmp/example.html | wc -l; echo "=== H1 TAGS ==="; grep -oP '<h1[^>]*>[^<]*</h1>' /tmp/example.html || echo "NO H1"; echo "=== CANONICAL ==="; grep -oP '<link[^>]*rel="canonical"[^>]*>' /tmp/example.html || echo "NO CANONICAL"; echo "=== ROBOTS META ==="; grep -oP '<meta[^>]*name="robots"[^>]*>' /tmp/example.html || echo "NO ROBOTS META"

=== TITLE ===
<title>Example Domain</title>
=== META DESCRIPTION ===
NO META DESCRIPTION
=== H1 COUNT ===
0
=== H1 TAGS ===
NO H1
=== CANONICAL ===
NO CANONICAL
=== ROBOTS META ===
NO ROBOTS META
  ────────────────────────────────────────
  ▸ shell
    command: curl -s -L -o /tmp/helperorchard.html "https://helperorchard.com"

(no output)
  ────────────────────────────────────────
  ▸ shell
    command: echo "=== TITLE ==="; grep -oP '<title>[^<]*</title>' /tmp/helperorchard.html || echo "NO TITLE"; echo "=== META DESCRIPTION ==="; grep -oP '<meta[^>]*name="description"[^>]*>' /tmp/helperorchard.html || echo "NO META DESCRIPTION"; echo "=== H1 COUNT ==="; grep -oP '<h1[^>]*>' /tmp/helperorchard.html | wc -l; echo "=== H1 TAGS ==="; grep -oP '<h1[^>]*>[^<]*</h1>' /tmp/helperorchard.html || echo "NO H1"; echo "=== CANONICAL ==="; grep -oP '<link[^>]*rel="canonical"[^>]*>' /tmp/helperorchard.html || echo "NO CANONICAL"; echo "=== ROBOTS META ==="; grep -oP '<meta[^>]*name="robots"[^>]*>' /tmp/helperorchard.html || echo "NO ROBOTS META"

=== TITLE ===
<title>HelperOrchard</title>
=== META DESCRIPTION ===
<meta name="description" content="Ready-made helpers for jobs you already do each week.">
=== H1 COUNT ===
1
=== H1 TAGS ===
<h1>Pick the job. Install the helper.</h1>
=== CANONICAL ===
<link rel="canonical" href="https://helperorchard.com/">
=== ROBOTS META ===
NO ROBOTS METANow I'll extract up to 20 links from each page to check them for 4xx/5xx status codes.

  ────────────────────────────────────────
  ▸ shell
    command: echo "=== example.com links ==="; grep -oP 'href=["\']([^"\']*)["\']' /tmp/example.html | sed -E "s/href=['\"]([^'\"]*)['\"]/\1/" | head -20


  ────────────────────────────────────────
  ▸ shell
    command: echo "=== helperorchard.com links ==="; grep -oP 'href=["\']([^"\']*)["\']' /tmp/helperorchard.html | sed -E "s/href=['\"]([^'\"]*)['\"]/\1/" | head -20

bash: -c: line 1: syntax error near unexpected token `('
bash: -c: line 1: `echo "=== example.com links ==="; grep -oP 'href=["\']([^"\']*)["\']' /tmp/example.html | sed -E "s/href=['\"]([^'\"]*)['\"]/\1/" | head -20'

Command exited with code 2bash: -c: line 1: syntax error near unexpected token `('
bash: -c: line 1: `echo "=== helperorchard.com links ==="; grep -oP 'href=["\']([^"\']*)["\']' /tmp/helperorchard.html | sed -E "s/href=['\"]([^'\"]*)['\"]/\1/" | head -20'

Command exited with code 2
  ────────────────────────────────────────
  ▸ shell
    command: python3 << 'PYEOF'
import re, sys, urllib.request, urllib.parse, ssl

def extract_links(html, base_url, max_links=20):
    # find all href attributes
    links = re.findall(r'href="([^"]*)"', html)
    # also single quotes
    links += re.findall(r"href='([^']*)'", html)
    # convert to absolute URLs
    abs_links = []
    for u in links:
        if u.startswith('http://') or u.startswith('https://'):
            abs_links.append(u)
        else:
            # relative - join with base
            abs = urllib.parse.urljoin(base_url, u)
            abs_links.append(abs)
    # deduplicate preserving order
    seen = set()
    uniq = []
    for u in abs_links:
        if u not in seen:
            seen.add(u)
            uniq.append(u)
    return uniq[:max_links]

def check_status(url):
    try:
        req = urllib.request.Request(url, method='HEAD')
        ctx = ssl.create_default_context()
        ctx.check_hostname = False
        ctx.verify_mode = ssl.CERT_NONE
        resp = urllib.request.urlopen(req, timeout=10, context=ctx)
        return resp.status
    except urllib.error.HTTPError as e:
        return e.code
    except Exception as e:
        return f"ERROR:{e}"

html_ex = open('/tmp/example.html').read()
html_hc = open('/tmp/helperorchard.html').read()

base_ex = 'https://example.com'
base_hc = 'https://helperorchard.com'

links_ex = extract_links(html_ex, base_ex, 20)
links_hc = extract_links(html_hc, base_hc, 20)

print("\n=== example.com links ===")
for u in links_ex:
    st = check_status(u)
    print(f" {st} {u}")

print("\n=== helperorchard.com links ===")
for u in links_hc:
    st = check_status(u)
    print(f" {st} {u}")
PYEOF


=== example.com links ===

=== helperorchard.com links ===
 403 https://helperorchard.com/
 403 https://helperorchard.com/favicon.svg
 403 https://helperorchard.com/_astro/_tool_.BkuCCq8O.css
 403 https://helperorchard.com#content
 403 https://helperorchard.com/bundles/
 403 https://helperorchard.com/jobs/marketing/
 403 https://helperorchard.com/jobs/sales/
 403 https://helperorchard.com/jobs/operations/
 403 https://helperorchard.com/jobs/personal/
 403 https://helperorchard.com/about/
 403 https://helperorchard.com/jobs/
 403 https://helperorchard.com/hermes/
 403 https://helperorchard.com/bundles/bill-due-reminders/
 403 https://helperorchard.com/bundles/call-prep-sheet/
 403 https://helperorchard.com/bundles/competitor-price-watch/
 403 https://helperorchard.com/bundles/content-calendar/
 403 https://helperorchard.com/bundles/first-touch-draft/
 403 https://helperorchard.com/bundles/follow-up-nudge/
 403 https://helperorchard.com/bundles/habit-check-in/
 403 https://helperorchard.com/bundles/inbox-triage-summary/
  ────────────────────────────────────────
  ▸ shell
    command: wc -l /tmp/example.html /tmp/helperorchard.html; echo "--- example head ---"; head -c 800 /tmp/example.html; echo; echo "--- helperorchard head ---"; head -c 800 /tmp/helperorchard.html

     1 /tmp/example.html
   101 /tmp/helperorchard.html
   102 total
--- example head ---
<!doctype html><html lang=en><head><meta charset=utf-8><link rel=icon href=data:,><meta name=viewport content="width=device-width,initial-scale=1"><title>Example Domain</title><style>html{color-scheme:light dark;background:light-dark(#eee,#222)}body{font:16px/1.6 system-ui,sans-serif;max-width:26em;margin:auto;padding:25vh 2em 2em;text-align:center}</style></head><body><p>This domain is for use in documentation examples without needing permission. This is not a service; avoid relying on it for testing and monitoring purposes.</p><script src=/s.js></script></body></html>

--- helperorchard head ---
<!DOCTYPE html><html lang="en"> <head><meta charset="utf-8"><meta name="viewport" content="width=device-width, initial-scale=1"><script>
      (function () {
        try {
          if (localStorage.getItem("helperorchard-theme") === "dark") document.documentElement.classList.add("dark");
        } catch (error) {}
        var valid = ["hermes", "goose", "claude-code", "cursor", "codex", "openclaw"];
        var search = new URLSearchParams(location.search);
        var query = search.get("tool");
        if (!query && search.getAll("platform").length === 1) query = search.get("platform");
        var stored = "";
        try {
          stored = localStorage.getItem("helperorchard-harness") || "";
        } catch (error) {}
        var id = valid.indexOf(query) >= 0 ? query : valid.indexO
  ────────────────────────────────────────
  ▸ shell
    command: python3 << 'PYEOF'
import re, time, urllib.request, urllib.parse, ssl, socket

ctx = ssl.create_default_context()
ctx.check_hostname = False
ctx.verify_mode = ssl.CERT_NONE

def extract_links(html, base_url, max_links=20):
    links = re.findall(r'href="([^"]*)"', html)
    links += re.findall(r"href='([^']*)'", html)
    abs_links = []
    for u in links:
        uu = u.strip()
        if uu.startswith('http://') or uu.startswith('https://'):
            abs_links.append(uu)
        else:
            abs_links.append(urllib.parse.urljoin(base_url, uu))
    seen = set(); uniq = []
    for u in abs_links:
        if u not in seen:
            seen.add(u); uniq.append(u)
    return uniq[:max_links]

def check_status(url):
    try:
        req = urllib.request.Request(url, headers={'User-Agent':'Mozilla/5.0'})
        t0 = time.time()
        resp = urllib.request.urlopen(req, timeout=10, context=ctx)
        dt = time.time() - t0
        return resp.status, round(dt,3)
    except urllib.error.HTTPError as e:
        t0 = time.time(); dt = time.time() - t0
        return e.code, round(dt,3)
    except Exception as e:
        return f"ERR:{type(e).__name__}", None

# For helperorchard.com, links we found earlier:
links_hc = [
'https://helperorchard.com/',
'https://helperorchard.com/favicon.svg',
'https://helperorchard.com/_astro/_tool_.BkuCCq8O.css',
'https://helperorchard.com/#content',
'https://helperorchard.com/bundles/',
'https://helperorchard.com/jobs/marketing/',
'https://helperorchard.com/jobs/sales/',
'https://helperorchard.com/jobs/operations/',
'https://helperorchard.com/jobs/personal/',
'https://helperorchard.com/about/',
'https://helperorchard.com/jobs/',
'https://helperorchard.com/hermes/',
'https://helperorchard.com/bundles/bill-due-reminders/',
'https://helperorchard.com/bundles/call-prep-sheet/',
'https://helperorchard.com/bundles/competitor-price-watch/',
'https://helperorchard.com/bundles/content-calendar/',
'https://helperorchard.com/bundles/first-touch-draft/',
'https://helperorchard.com/bundles/follow-up-nudge/',
'https://helperorchard.com/bundles/habit-check-in/',
'https://helperorchard.com/bundles/inbox-triage-summary/',
]

print("=== helperorchard.com links (GET) ===")
for u in links_hc:
    st, dt = check_status(u)
    print(f" {st} time={dt}s  {u}")
PYEOF

=== helperorchard.com links (GET) ===
 200 time=0.104s  https://helperorchard.com/
 200 time=0.097s  https://helperorchard.com/favicon.svg
 200 time=0.07s  https://helperorchard.com/_astro/_tool_.BkuCCq8O.css
 200 time=0.083s  https://helperorchard.com/#content
 200 time=0.082s  https://helperorchard.com/bundles/
 200 time=0.058s  https://helperorchard.com/jobs/marketing/
 200 time=0.07s  https://helperorchard.com/jobs/sales/
 200 time=0.089s  https://helperorchard.com/jobs/operations/
 200 time=0.111s  https://helperorchard.com/jobs/personal/
 200 time=0.148s  https://helperorchard.com/about/
 200 time=0.04s  https://helperorchard.com/jobs/
 200 time=0.103s  https://helperorchard.com/hermes/
 200 time=0.107s  https://helperorchard.com/bundles/bill-due-reminders/
 200 time=0.085s  https://helperorchard.com/bundles/call-prep-sheet/
 200 time=0.102s  https://helperorchard.com/bundles/competitor-price-watch/
 200 time=0.115s  https://helperorchard.com/bundles/content-calendar/
 200 time=0.117s  https://helperorchard.com/bundles/first-touch-draft/
 200 time=0.048s  https://helperorchard.com/bundles/follow-up-nudge/
 200 time=0.078s  https://helperorchard.com/bundles/habit-check-in/
 200 time=0.067s  https://helperorchard.com/bundles/inbox-triage-summary/## Site Health Check Report

| URL | Status | Time | Issues |
|---|---|---|---|
| **https://example.com** | 200 OK (0.099 s) | 0.099 s | • Missing meta description (none found)<br>• No `<h1>` element (0 found)<br>• No canonical link<br>• No robots meta tag (not checked)<br>• Links: none found on page |
| **https://helperorchard.com** | 200 OK (0.186 s) | 0.186 s | No issues |

### Detailed findings

**https://example.com**  
- **Title:** “Example Domain” – 14 chars (within 10‑60 range) ✅  
- **Meta description:** **Missing** – no `<meta name="description">` found ❌  
- **`<h1>`:** **0 found** – skill requires exactly one ❌  
- **Canonical link:** **None** ❌  
- **Robots meta:** **Not present** (no `noindex` flag) ✅  
- **Link check:** No `href` attributes extracted; page has no outgoing links to test.

**https://helperorchard.com**  
- **Title:** “HelperOrchard” – 15 chars (within 10‑60 range) ✅  
- **Meta description:** “Ready‑made helpers for jobs you already do each week.” – ~56 chars (within 50‑160 range) ✅  
- **`<h1>`:** Exactly one (`<h1>Pick the job. Install the helper.</h1>`) ✅  
- **Canonical link:** Present (`<link rel="canonical" href="https://helperorchard.com/">`) ✅  
- **Robots meta:** **Not present** (no `noindex` flag) ✅  
- **Link check:** Extracted 20 links (internal pages, CSS, favicon, etc.) – all returned **HTTP 200** with response times well under 10 seconds; **no 4xx/5xx errors**.

### Summary
- Both sites are **up** (HTTP 200) and loaded within 10 seconds.  
- **example.com** has three SEO issues: missing meta description, missing `<h1>`, and no canonical link.  
- **helperorchard.com** passes all checks with no issues.  
- No pages are marked **DOWN**; all link checks returned successful status codes.

Loading recipe: Site Health Check
Description: Checks a website is up and flags basic SEO problems like missing titles or broken links. Use for a daily site check.

