# 08 — Staged Release + Portfolio Write-up

## Staged release plan

Release in stages. Do not go straight to a wide release. Each stage has a clear size, duration, check, and a rule for whether to continue, fix, or pause.

### Stage 1 — You + 3 students, 2 weeks

- **Who:** You and 3 students.
- **Duration:** 2 weeks.
- **What happens:** Every extraction is human-confirmed. This is the design, not just the test — no deadline is saved without student confirmation at any stage.
- **What to measure:**
  - Deadline extraction accuracy (pre- and post-confirmation) on real documents.
  - Attendance arithmetic — checked by hand.
  - Whether students understand the digest and the attendance figures.
  - Any privacy or usability problems.
- **Exit check:** No critical failures (wrong deadline saved, wrong attendance maths, privacy incident). Students can explain, in their own words, what the attendance figure means.
- **Decision:** Continue to Stage 2 / Fix and repeat Stage 1 / Pause.

### Stage 2 — 30-student cohort, advisor review

- **Who:** 30 students, plus one academic advisor / tutor.
- **Duration:** One teaching block or semester period — define the exact length before starting (for example, 6 weeks).
- **What happens:**
  - Students use the assistant weekly; every extraction is still human-confirmed.
  - The advisor reviews **anonymised** warning accuracy weekly — no student can be identified from the review data.
  - Advisor escalation only with individual student consent.
  - Measure the missed-deadline rate against the self-reported baseline collected before the pilot (see `05-metrics.md`).
- **What to measure (weekly):**
  - Warning precision (correct warnings / all warnings).
  - Missed warnings (at-risk students who received no warning).
  - Digest open rate and action rate.
  - Cost per student per month.
  - Any harm: false reassurance, wrong deadlines, privacy incidents, alert fatigue.
- **Exit check:** Warning precision ≥90%.
- **Decision:** Continue to Stage 3 / Fix and repeat Stage 2 / Pause.

### Stage 3 — Wider release

- **Who:** A wider group — define the size before starting (for example, a full year group or department).
- **Gate:** Wider release **only if warning precision is ≥90% in Stage 2.** If it is below 90%, do not proceed. Fix the problem and repeat Stage 2.
- **What happens:** Same human-in-the-loop design. Same weekly digest limit. Same privacy guardrails. Continue measuring warning precision, missed-deadline rate, cost, and harm weekly for the first month.

## Decision log

Record each stage decision here, with the evidence behind it.

| Stage | Date | Decision (continue / fix / pause) | Evidence | Next step |
|---|---|---|---|---|
| Stage 1 | TBD | TBD | TBD | TBD |
| Stage 2 | TBD | TBD | TBD | TBD |
| Stage 3 | TBD | TBD | TBD | TBD |

## Fix / pause / continue recommendation — TEMPLATE

Complete this at the end of the pilot. Do not write it before you have results.

**Recommendation:** TBD — Continue / Fix and repeat / Pause.

**Evidence for the recommendation:**

- Deadline accuracy post-confirmation: TBD (target ≥98%)
- Warning precision in Stage 2: TBD (target ≥90%)
- Attendance arithmetic: TBD (target 100%)
- Missed-deadline rate vs baseline: TBD
- Digest open + action rate: TBD
- Cost per student per month: TBD
- Harm incidents: TBD (target 0 false reassurance, 0 privacy incidents)

**What we would fix next:**

1. TBD
2. TBD

**What we would not change:**

1. TBD

**What would make us pause:**

- Warning precision below 90% in Stage 2.
- Any privacy incident, or any case of false reassurance.
- A wrong deadline that causes a missed submission.
- Costs far above the budget in `06-cost-latency.md` with no clear fix.

## Portfolio write-up

### What I built

The Student Success Assistant: an AI Product Manager design project that helps students track deadlines and attendance, with early warnings they can trust. The AI extracts deadlines from notices, emails, and LMS posts; the student confirms every extraction before it is saved; the system calculates attendance with visible arithmetic; and one weekly digest lists what is due, what is at risk, and one action per risk.

### The problem

Students miss deadlines because announcements are spread across class, email, the LMS, and notice boards — and they discover attendance shortfalls too late to recover. A wrong warning, or a missed one, destroys trust.

### What I did

1. Defined the problem and the evidence needed (`01-problem-statement.md`).
2. Interviewed 5 students (including one who had missed a deadline or an attendance threshold) and 1 advisor, mapped every deadline channel, and recorded the real attendance rule (`02-research-notes.md`).
3. Wrote a one-page spec with a human-in-the-loop workflow and clear out-of-scope limits (`03-spec.md`).
4. Built a 50-document eval set and a 10-case attendance audit, with a wrong deadline counted as a critical failure (`04-eval.md`, `evals/eval-set.csv`).
5. Planned metrics for task success, quality, cost per success, and harm (`05-metrics.md`).
6. Estimated cost and latency, including a 500-student pilot budget and cost controls (`06-cost-latency.md`).
7. Listed risks and guardrails, including privacy, false reassurance, and alert fatigue (`07-risks-guardrails.md`).
8. Planned a staged release with a clear gate for wider release (`08-release-portfolio.md` — this file).

### What I learned

- TBD — complete after the pilot. What surprised you? What would you do differently?
- TBD

### Portfolio proof checklist

| Proof | File | Status |
|---|---|---|
| Channel map from research | `docs/02-research-notes.md` | TBD — complete after interviews |
| Workflow diagram (AI alone / AI + confirm / human only) | `docs/03-spec.md` | Included |
| 50-document eval log | `evals/eval-set.csv` + `docs/04-eval.md` | Test set included; results TBD |
| Attendance calculation audit | `docs/04-eval.md` | Template included; audit TBD |
| Privacy note | `docs/07-risks-guardrails.md` | Included |
| Pilot results | `docs/05-metrics.md`, this file | TBD — complete after pilot |
| Fix / pause / continue recommendation | This file | TBD — complete after pilot |

### How to review this project

Start with the `README.md`, then read the spec (`03-spec.md`) and the eval (`04-eval.md`). The research notes and release plan show how the design was tested and how it would be released safely.
