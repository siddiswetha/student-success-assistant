# 03 — One-Page Spec

## Product

**Student Success Assistant** — Deadlines, Attendance & Early Warning.

A student provides notices, emails, or LMS posts. The assistant extracts the deadline, the student confirms it, and the system tracks deadlines and attendance in one place, with one weekly digest.

## Problem (one paragraph)

Students miss deadlines because announcements are spread across class, email, the LMS, and notice boards, and they discover attendance shortfalls too late to recover. Early, accurate warning gives students and advisors time to act. A wrong warning, or a missed one, destroys trust.

## Users

- **Primary:** Students.
- **Secondary (with student consent only):** Academic advisors / tutors.

## Workflow — human-in-the-loop

```
Student provides a notice / email / LMS post
        ↓
AI extracts: assignment title, subject, deadline, source
        ↓
STUDENT CONFIRMS every extraction before it is saved
        ↓  (student corrects it if wrong; nothing is saved unconfirmed)
Saved deadline appears in the student's list
        ↓
System calculates attendance % and classes needed to recover,
showing the arithmetic
        ↓
Once a week: digest — due this week, at-risk subjects,
one suggested action per risk
```

### Workflow diagram — who does what

| Step | AI alone | AI + human confirm | Human only |
|---|---|---|---|
| Extract title, subject, deadline, source from a document | Draft extraction | — | — |
| Confirm or correct the extraction | — | **Student confirms before saving** | — |
| Save the deadline | — | After confirmation | — |
| Calculate attendance % and recovery classes | Calculation (shown) | Student checks the arithmetic | — |
| Decide the suggested action in the digest | Draft suggestion | — | Student decides whether to act |
| Contact faculty, submit work, share data with an advisor | — | — | **Human only, with consent** |

The rule is simple: **the AI suggests, the human decides.** No deadline is saved without confirmation. No advisor sees data without student consent.

## Attendance calculation — show the work

Every attendance figure must show:

- Attended classes: X
- Total classes recorded: Y
- Calculation: X ÷ Y × 100 = Z%
- Label: "based on X of Y classes recorded"
- Classes needed to recover to the threshold (for example, to reach 75%)

**EXAMPLE (illustrative only):**
> EXAMPLE: Attended 18 of 24 classes recorded. 18 ÷ 24 × 100 = 75%. Based on 18 of 24 classes recorded. To stay at or above 75% after the next 4 classes, attend at least 3 of them.

If attendance data is incomplete, the system must say so clearly. It must never say "you're fine" when data is missing.

## Weekly digest

One digest per week, maximum. It contains:

1. Due this week (title, subject, deadline, source).
2. At-risk subjects (attendance below, or close to, the threshold).
3. One suggested action per risk (for example, "Attend the next 3 classes in Subject X to return to 75%").

No more than one digest per week. No extra alerts unless the student asks for them.

## In scope

- Extract title, subject, deadline, and source from notices / emails / LMS posts the student provides.
- Student confirmation of every extraction before saving.
- Attendance % calculation with visible arithmetic and recovery classes.
- Weekly digest (due this week, at-risk subjects, one action per risk).
- Student-only data store, with one-tap delete of all data.
- Advisor escalation only with student consent.

## Out of scope

- No automatic submission of assignments.
- No contacting faculty on the student's behalf.
- No prediction of grades.
- No automatic sharing of student data with advisors, parents, or the university.
- No daily or real-time alerts (weekly digest only, by design).

## Primary metric

- **Deadline extraction accuracy** (before and after human confirmation), **plus**
- **% of at-risk warnings that were correct and timely.**

Both must be measured. Extraction accuracy alone is not enough — a warning that is correct but too late is still a failure.

## Pass bar

- ≥98% deadline accuracy **after** human confirmation.
- 100% attendance arithmetic (verified by hand on 10 cases — see `04-eval.md`).
- Stage 3 release only if warning precision is ≥90% in Stage 2 (see `08-release-portfolio.md`).

## Open questions

- What is the exact attendance rule in your institution? (Confirm in `02-research-notes.md` — do not assume.)
- Which channels matter most for your students? (Confirm from the channel map.)
- What counts as "timely" for a warning? Define it in the pilot before measuring it.
