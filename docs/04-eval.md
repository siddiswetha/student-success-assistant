# 04 — Eval Test Set + Rubric + Results

## What we are testing

Two things, separately:

1. **Deadline extraction** — can the AI correctly pull the title, subject, and deadline from a document?
2. **Attendance maths** — is the attendance calculation always correct?

Both matter. A wrong deadline is a critical failure. Wrong attendance maths is also a critical failure, because a student may act on a wrong number.

## Test set 1 — 50-document extraction test set

**File:** `evals/eval-set.csv`
**Size:** Exactly 50 rows (plus a header row).
**All documents are marked EXAMPLE.** They are test inputs, not real student documents.

### What the 50 documents cover

| Category | Rows | What it tests |
|---|---|---|
| Clean emails | 15 | Clear, well-written emails with one deadline each |
| Photographed handwritten notices | 10 | Handwriting, photos, unclear text — the hardest input to read |
| Ambiguous dates ("next Friday", "tomorrow", "end of week") | 15 | Dates that need a reference date to resolve correctly |
| Duplicate announcements with a corrected deadline | 10 | Two versions of the same deadline; the corrected one must win |
| **Total** | **50** | |

For ambiguous dates, record the reference date used (for example, "document received on Monday 2026-11-02, so 'next Friday' means 2026-11-13"). Without a reference date, an ambiguous date cannot be scored fairly.

For duplicates, the expected deadline is the **corrected** deadline, and the notes column explains which announcement came later.

### Columns in `evals/eval-set.csv`

| Column | Meaning |
|---|---|
| `id` | Unique ID, e.g. E01–E50 |
| `document_type` | clean_email / handwritten_notice / ambiguous_date / duplicate_correction |
| `document_text` | The full EXAMPLE document text |
| `expected_title` | The correct assignment title |
| `expected_subject` | The correct subject |
| `expected_deadline` | The correct deadline (YYYY-MM-DD, plus time if given) |
| `rubric` | Which fields are scored for this row |
| `result` | **Blank / TBD — fill in after running the test. Do not invent results.** |
| `notes` | Reference date, correction history, or other scoring notes |

### Rubric — score each field separately

For each document, score title, subject, and deadline separately:

| Field | Correct | Partially correct | Wrong / missing |
|---|---|---|---|
| Title | Exact assignment title | Close but not exact (e.g. missing a word) | Wrong title, or none extracted |
| Subject | Correct subject | Right area, wrong subject name | Wrong subject, or none extracted |
| Deadline | Correct date (and time, if given) | Right day, wrong time — or vice versa | **Wrong date = critical failure** |

**A wrong deadline is a critical failure**, even if the title and subject are correct. One wrong deadline can cause a missed submission. Count critical failures separately from other errors.

### How to run the test

1. Take one document at a time from `evals/eval-set.csv`.
2. Give the document to the assistant exactly as written. Do not add hints.
3. Record what the assistant extracted (title, subject, deadline) **before** human confirmation.
4. Then confirm or correct it as a student would, and record the result **after** confirmation.
5. Score each field. Mark any wrong deadline as a critical failure.
6. Do not change the expected answers to match the assistant's output.

### Results table — fill in after running the test (do not invent)

| Measure | Pre-confirmation | Post-confirmation | Target |
|---|---|---|---|
| Title accuracy (correct / 50) | TBD | TBD | — |
| Subject accuracy (correct / 50) | TBD | TBD | — |
| Deadline accuracy (correct / 50) | TBD | TBD | ≥98% post-confirmation |
| Critical failures (wrong deadline) | TBD | TBD | 0 post-confirmation |
| Clean emails — deadline accuracy | TBD | TBD | — |
| Handwritten notices — deadline accuracy | TBD | TBD | — |
| Ambiguous dates — deadline accuracy | TBD | TBD | — |
| Duplicate corrections — deadline accuracy | TBD | TBD | — |

### What we learned from the eval — fill in after running it

- Most common error type: TBD
- Errors on handwritten notices: TBD
- Errors on ambiguous dates: TBD
- Errors on duplicates: TBD
- Fix we will make before the pilot: TBD

## Test set 2 — Attendance-maths audit (10 cases, checked by hand)

The attendance calculation must be 100% correct. Verify it by hand on 10 cases — do not trust the system to check itself.

### Audit template

For each case, fill in the attended count, total recorded, hand-calculated percentage, system-calculated percentage, and whether they match. Also fill in the recovery calculation by hand.

| Case | Subject (EXAMPLE) | Attended (X) | Total recorded (Y) | Hand calculation: X ÷ Y × 100 | Hand result | System result | Match? | Classes needed to recover (hand) | System recovery | Match? |
|---|---|---|---|---|---|---|---|---|---|---|
| A01 | TBD | | | | | | TBD | | | TBD |
| A02 | TBD | | | | | | TBD | | | TBD |
| A03 | TBD | | | | | | TBD | | | TBD |
| A04 | TBD | | | | | | TBD | | | TBD |
| A05 | TBD | | | | | | TBD | | | TBD |
| A06 | TBD | | | | | | TBD | | | TBD |
| A07 | TBD | | | | | | TBD | | | TBD |
| A08 | TBD | | | | | | TBD | | | TBD |
| A09 | TBD | | | | | | TBD | | | TBD |
| A10 | TBD | | | | | | TBD | | | TBD |

**Include edge cases in the 10:** a student at exactly the threshold, a student just below it, a student with very few classes recorded, and a student with incomplete data (where the system must say "based on X of Y classes recorded" and must not say "you're fine").

### Attendance audit results — fill in after checking

| Measure | Result | Target |
|---|---|---|
| Attendance % correct (out of 10) | TBD | 10 / 10 (100%) |
| Recovery classes correct (out of 10) | TBD | 10 / 10 (100%) |
| Incomplete-data cases handled correctly | TBD | All |

If any case fails, stop. Fix the calculation and re-run all 10 cases by hand before continuing.

## Pass / fail

- **Pass:** ≥98% deadline accuracy after human confirmation, 0 critical failures post-confirmation, and 100% attendance arithmetic.
- **Fail:** Below any of those bars. Record what failed, fix it, and re-run the full test set — do not re-run only the failed rows.
