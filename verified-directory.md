# VERIFIED-DIRECTORY.md — the '5-Minute Verified' public directory

**Where it lives:** the SEO site — `jtabsbm.github.io/callbackops-tools/verified/`
(one page per business + this index). Every badge embed on a client site links to
its entry here, which makes the directory the badge's proof-of-work **and** the
program's backlink engine: each verified business = one inbound link from a real
local-business site to our domain.

**Publishing gate (honesty rule):** a business appears in the public directory
only after it opts in to the program. The ten entries below are the **seed
list** — real San Diego businesses already in our outreach pipeline
(`pipeline.csv`), queued for a program invite. They are marked `AUDIT PENDING ·
INVITE STAGE` in this internal file; they go live on the site in the same format
with `AUDIT PENDING` the moment they say yes, and flip to `VERIFIED 20XX` only on
a passing audit. No business is ever listed as verified before its audit closes.

---

## Directory index format (page: `/verified/`)

```markdown
# 5-Minute Verified — San Diego

Independent response-time verification for local businesses. Median callback
under 5 minutes, p95 under 15, zero over an hour — measured over 7 days,
re-verified monthly, revocable. [What this means →](#standard)

## Verified (N)

| Business | Trade | City | Verified since | Median | p95 | Max | Audit ID |
|---|---|---|---|---|---|---|---|
| — none yet — the first audits close after program invites | | | | | | | |

## Audit pending (N)

| Business | Trade | City | Status | In program since |
|---|---|---|---|---|
| ... | ... | ... | audit pending | 20XX-XX-XX |
```

## Per-entry page format (page: `/verified/<business-slug>/`)

```markdown
# <Business Name> — 5-Minute Verified

[badge SVG inline — 140px]

**Status:** VERIFIED 20XX (valid through MM/DD · re-verified monthly)
**Trade:** HVAC · **City:** San Diego, CA
**Audit window:** MM/DD–MM/DD · **Audit ID:** SD-2026-001

| Metric (business-hours first-callback lag) | Result | Standard |
|---|---|---|
| Median | 3.2 min | < 5 min ✅ |
| p95 | 11.4 min | < 15 min ✅ |
| Max | 18.0 min | — |
| Events > 60 min | 0 | 0 required ✅ |
| Events audited | 47 | ≥ 25 ✅ |

Per-day table + methodology: [AUDIT-PROTOCOL.md]. Raw logs are never published.

**History:** month-by-month pass/fail trail (the revocation record — public).
```

Aggregate-only disclosure: entries show the stats above; raw call logs stay in
the audit workspace permanently.

---

## SEED LIST — first 10 entries (internal, invite stage)

Real pipeline prospects (`pipeline.csv`, San Diego metro) chosen across trades
where missed-call speed decides revenue — each gets the program invite email
(README § outreach) with this directory page attached:

| # | Business | Trade | City | Status |
|---|---|---|---|---|
| 1 | Atlas HVAC | HVAC | San Diego, CA | AUDIT PENDING · invite stage |
| 2 | Same Day Heating Cooling & Plumbing | HVAC/Plumbing | San Diego, CA | AUDIT PENDING · invite stage |
| 3 | Mr. Rooter Plumbing of San Diego | Plumbing | San Diego, CA | AUDIT PENDING · invite stage |
| 4 | San Diego Roofing Inc. | Roofing | San Diego, CA | AUDIT PENDING · invite stage |
| 5 | AER Electric | Electrical | San Diego, CA | AUDIT PENDING · invite stage |
| 6 | Garage Door Medics (GD Medics) | Garage doors | San Diego, CA | AUDIT PENDING · invite stage |
| 7 | 858 Appliance Repair | Appliance repair | San Diego, CA | AUDIT PENDING · invite stage |
| 8 | Splash Pro Pools | Pool service | San Diego, CA | AUDIT PENDING · invite stage |
| 9 | Revive Med Spa | Med spa | San Diego, CA | AUDIT PENDING · invite stage |
| 10 | Anderson Plumbing Heating & Air | HVAC/Plumbing | San Diego, CA | AUDIT PENDING · invite stage |

All 10 are already in `pipeline.csv` (46 unique SD businesses available — the
next 36 are the waitlist for wave 2 of invites).

## Status vocabulary (matches CERTIFY.md)

- `VERIFIED 20XX` — passed the current audit cycle (green badge, year shown)
- `AUDIT PENDING` — opted in, audit not yet passed (gray badge, directory only)
- `VERIFICATION LAPSED` — 30+ days unverified (entry stays, badge must come down)
- `REVOKED` — failed re-audit; kept in history, marked revoked (honesty > sunk cost)

## SEO mechanics

- **One page per business** → long-tail queries ("<business> response time",
  "<trade> that answers the phone san diego") with the badge asset as the
  page's visual; the per-entry pages are the ones local sites link to when
  embedding the badge.
- **Structured data:** each verified entry ships `LocalBusiness` +
  `Review`-free aggregate stats (no fake review schema — numbers only, sourced
  from the audit).
- **The backlink loop:** embed code (BADGE-ASSETS.html) links the badge → the
  business's entry → the standard. Every new verified business adds one
  real-local-domain inbound link. 10 verified businesses = 10 links + a
  directory page that ranks for "answers the phone" intent in every trade.
- **Indexing:** new entries pinged via the existing `indexnow-submit.py` flow.

---

*Directory is honest by construction: it publishes failures and revocations,
not just passes. That is the whole reason a consumer or SEO should trust it.*
