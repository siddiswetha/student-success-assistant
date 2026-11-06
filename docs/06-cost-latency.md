# 06 — Cost & Latency Estimate

> **Note:** All prices below are placeholders to be replaced with real prices from the provider you actually use. Do not present placeholder prices as real quotes. Check the provider's current pricing page before committing to a budget, and record the date you checked it.

## What costs money

1. **Document extraction** — each time the AI reads a notice, email, or LMS post and extracts the title, subject, deadline, and source.
2. **Weekly digest generation** — once per student, once per week.
3. **Storage** — student data, stored for the student only.

What does **not** cost money per use in this design: viewing a saved deadline, viewing attendance, or opening a digest that has already been generated.

## Cost model

| Item | Unit cost (TBD — fill in real price) | Units | Cost |
|---|---|---|---|
| Cost per document extraction | $____ per document | ____ documents per student per semester | $____ per student per semester |
| Weekly digest generation | $____ per digest | 1 per student per week × ____ weeks | $____ per student per semester |
| Storage | $____ per student per month | ____ months | $____ per student per semester |
| **Total per student per semester** | | | **$____** |
| **Total per student per month** | | | **$____** |

### Worked example — how to calculate it (EXAMPLE numbers only)

> EXAMPLE (illustrative only — replace with real prices):
> If one extraction costs $0.02 and a student uploads 30 documents per semester, extraction costs 30 × $0.02 = $0.60 per student per semester.
> If one digest costs $0.05 and there are 15 teaching weeks, digest costs 15 × $0.05 = $0.75 per student per semester.
> Total: $0.60 + $0.75 = $1.35 per student per semester (plus storage, if any).

## Budget for a 500-student pilot

Fill in the table with real prices. The formula is:

**Pilot cost = (cost per student per semester) × 500**

| Item | Per student per semester | × 500 students | Pilot total |
|---|---|---|---|
| Document extraction | $____ | | $____ |
| Weekly digest | $____ | | $____ |
| Storage | $____ | | $____ |
| **Pilot total** | **$____** | | **$____** |
| Contingency (add 20% for re-runs, corrections, and longer documents) | | | $____ |
| **Pilot total with contingency** | | | **$____** |

Assumptions to record (fill in with your real assumptions):

- Documents per student per semester: TBD (ask students in research; do not guess — start with a range, e.g. 20–40, and refine it)
- Teaching weeks per semester: TBD
- Average document length: TBD
- Price checked on: TBD (date) — source: TBD (provider pricing page)

## Cost controls — what we chose, and why

| Control | What it does | Why it matters |
|---|---|---|
| Extract on upload only | The AI runs only when a student uploads a document. It never scans in the background. | No surprise cost from documents the student never provided. |
| Digest generated once weekly, not per open | The digest is generated once, then stored. Opening it again costs nothing. | A popular digest does not become expensive. |
| One digest per week, maximum | No daily or real-time alerts. | Controls cost and prevents alert fatigue at the same time. |
| Student confirms before saving | A wrong extraction is corrected before it is saved, not re-extracted many times. | Avoids paying to re-run the same document repeatedly. |
| No automatic re-extraction | If a document fails, the student is told — the system does not silently retry. | Prevents runaway cost from a single bad document. |

## Latency — how long the student waits

| Action | Target | Why |
|---|---|---|
| Extraction after upload | Under 30 seconds (target — confirm with real testing) | A student uploading a notice should not wait minutes. If it takes longer, say so clearly. |
| Attendance calculation | Instant (it is arithmetic, not AI) | There is no reason to wait for a calculation. |
| Weekly digest | Delivered on the same day and time each week | Predictability matters more than speed. Students should know when to expect it. |

Latency is not the main risk in this project — accuracy is. A fast wrong deadline is worse than a slow correct one. Do not trade accuracy for speed.

## What to do if costs rise

1. Check whether documents are being uploaded more often than expected, and why.
2. Check whether long documents (for example, a full photographed notice board) are costing more than short ones.
3. Do not cut the human-confirmation step to save money — that step is what keeps accuracy at ≥98%.
4. If the pilot budget is exceeded, pause new enrolment and review the cost model before continuing (see `08-release-portfolio.md`).
