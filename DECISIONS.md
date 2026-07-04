# Unhidden — Decisions & Starting Point

This file is the single source of truth for calls we've already made. If something isn't here, it's still open — flag it as a GitHub Issue rather than guessing or waiting on a call.

---

## What Unhidden is (one paragraph)

Unhidden is a pay equity platform built on three connected surfaces: the **Index** (a free, public, citation-backed calculator showing the lifetime structural cost of being a woman in Sweden — this drives trust and reach), **Unhidden for Employers** (paid B2B SaaS automating lönekartläggning and EU Pay Transparency Directive compliance), and **Unhidden Verified + Directory** (certification for employers who close their gap, listed publicly). The Index is the strategic core — it earns the credibility that makes the SaaS and certification mean something. We're building a standard, not just a compliance tool.

---

## Your scope: Unhidden for Employers

You own `/employer-app`. Full autonomy on implementation — no need to check in on technical decisions inside that folder.

**What exists already:** a fictional-company MVP demo (pay gap analysis + certification status) — this is a proof of concept, not production code. Treat it as a spec of intent, not a foundation to build on unless you decide it's worth keeping.

**What it needs to do, per the pitch:**
1. Ingest company payroll data
2. Analyse the gap by role, seniority, department
3. Output a roadmap: which salary adjustments close how much of the gap, on what timeline
4. Track progress toward the certification threshold (≤2% adjusted gap)

**Reference the Index's calculation logic first.** The `dynamic()` function in `/index/eqly_index_sv.html` already implements structural gap math cited to Medlingsinstitutet, Försäkringskassan, and Pensionsmyndigheten (pay gap, parental leave loss, VAB asymmetry, pension impact). It's built for individuals, not companies, but the underlying formulas and source logic are the same ones the SaaS needs at company scale. Don't reverse-engineer this from the pitch doc — read the code.

**Build-from-scratch vs. extend the existing MVP demo: your call.** Caroline has no preference here — treat the demo as a spec of intent, not a foundation you're expected to preserve. Use whichever gets you to a working v1 fastest.

---

## Confirmed technical decisions

- **Index = static HTML/JS (Path A).** Fast iteration, no GDPR complexity, nothing stored or transmitted client-side. This is fixed — don't propose migrating it to a framework or backend.
- **Python is reserved for the Employer SaaS backend only.** This is your domain.
- **Hosting targets:** `eqly.eu` / `unhidden.eu` (not yet registered — see Open Items)
- **Certification threshold:** ≤2% adjusted pay gap, verified annually, with a documented action plan
- **No conflicts of interest model** — SaaS revenue (2,500–12,000 SEK/month by size) + certification fees (15,000–25,000 SEK/year for SMBs); Index stays free and non-revenue-generating by design

---

## Repo structure

- `/index` — Caroline owns. Public calculator, copy, citations.
- `/employer-app` — You own. Python SaaS.
- `/docs` — Shared reference. Pitch doc, concept paper, this file.

Use GitHub Issues as the sync point instead of ad hoc check-ins — unassigned issues are open for you to pick up.

---

## Equity (for reference, not yet formalized in a shareholders' agreement)

Founders combined 60–65%, developer 15–20%, marketer 8–12%, all on 4-year vesting with a 1-year cliff. Shareholders' agreement is on the to-do list before any external design partners are approached — flag if you want input before it's drafted.

---

## Open items (not yet decided — don't assume)

- `unhidden.eu` / `unhidden.se` domain registration — pending
- Unhidden AB company registration via Bolagsverket — pending
- Trademark check for "Unhidden" via PRV and EUIPO — pending
- Design partner pilots (3 Swedish mid-market companies, 50–300 employees) — not yet started
- Broader monetisation strategy (Substack, workshops, consulting, licensing) — still being developed

If any of these affect what you're building (e.g. company registration status affecting what the SaaS can legally invoice for), raise it as an Issue rather than assuming an answer.
