# 07 — Risk & Guardrails List

## How to use this list

For each risk: what could go wrong, who is harmed, how likely and serious it is, and the guardrail that prevents or reduces it. Review this list before every stage of the release (see `08-release-portfolio.md`).

## Risks

### 1. Privacy — notices and photos may contain other students' names

- **What could go wrong:** A student uploads a photographed notice or a forwarded email that contains other students' names, grades, or personal details. That data is then stored or processed without those students' consent.
- **Who is harmed:** The other students named in the document, and the student who uploaded it.
- **Guardrails:**
  - Student-only data store: each student's data is visible only to that student.
  - Store only the extracted deadline (title, subject, deadline, source), not the full document, unless the student explicitly asks to keep it.
  - One-tap delete of all data: the student can delete everything, immediately, without contacting anyone.
  - Tell students during onboarding: "Do not upload documents that contain other students' personal information unless you have removed it first."
  - Advisor access only with student consent, and only to the at-risk summary — never to raw documents.

### 2. False reassurance — "you're fine" when attendance data is incomplete

- **What could go wrong:** Attendance data covers only some classes. The system calculates a percentage from incomplete data and tells the student they are safe, when in fact they are below the threshold.
- **Who is harmed:** The student, who stops attending because they believe they are safe.
- **Guardrails:**
  - Show "based on X of Y classes recorded" on **every** attendance figure, with no exceptions.
  - If data is incomplete, say so in plain language: "This is based on 12 of 20 classes recorded. It may not be your true attendance."
  - Never display "you're fine" or a green "safe" label when data is incomplete.
  - The recovery calculation must also state how many classes it is based on.

### 3. Alert fatigue — students stop reading the digest

- **What could go wrong:** Too many messages, or messages that are not useful, teach students to ignore the system. Then a genuinely urgent warning is also ignored.
- **Who is harmed:** Students who miss a real warning because they learned to ignore all of them.
- **Guardrails:**
  - Maximum one digest per week.
  - No daily or real-time alerts.
  - One suggested action per risk — not a long list.
  - If digest open rates fall, investigate and fix the digest before adding more messages. Do not add more messages to fix low engagement.

### 4. Wrong deadline saved — a missed submission

- **What could go wrong:** The AI extracts the wrong date, the student does not notice during confirmation, and the deadline is saved wrong. The student misses the real deadline.
- **Who is harmed:** The student.
- **Guardrails:**
  - Student confirms every extraction before it is saved (human-in-the-loop, by design).
  - Show the source document alongside the extraction, so the student can check it.
  - A wrong deadline is a critical failure in the eval (see `04-eval.md`).
  - Pass bar: ≥98% deadline accuracy after human confirmation; 0 critical failures post-confirmation in the eval.
  - If a wrong deadline is discovered after saving, the student can correct or delete it immediately.

### 5. Wrong attendance maths — a student acts on a wrong number

- **What could go wrong:** The calculation is wrong, and a student attends (or skips) classes based on a wrong percentage.
- **Who is harmed:** The student.
- **Guardrails:**
  - Show the arithmetic on every figure, so the student can check it.
  - Verify by hand on 10 cases before release, and re-verify after any change to the calculation (see `04-eval.md`).
  - Pass bar: 100% attendance arithmetic.

### 6. Ambiguous dates resolved wrongly

- **What could go wrong:** "Next Friday", "tomorrow", or "end of week" is resolved to the wrong date because the reference date was unclear.
- **Who is harmed:** The student, who plans for the wrong day.
- **Guardrails:**
  - Always record the reference date used to resolve an ambiguous date.
  - Show the resolved date to the student during confirmation, with the original wording ("next Friday" → Friday 2026-11-13).
  - If the date cannot be resolved confidently, ask the student instead of guessing.

### 7. Duplicate announcements — the old deadline wins

- **What could go wrong:** A deadline is corrected (for example, moved from Friday to Monday), but the system keeps the old date because it saw the first announcement.
- **Who is harmed:** The student, who submits on the wrong day.
- **Guardrails:**
  - Test duplicates explicitly in the eval (10 of 50 documents).
  - When two announcements conflict, show both to the student and ask which is correct. Do not pick silently.
  - The corrected deadline is the expected answer in the eval.

### 8. Advisor escalation without consent

- **What could go wrong:** An advisor is told a student is at risk before the student has agreed to share that information.
- **Who is harmed:** The student, whose trust in the system — and in the advisor — is damaged.
- **Guardrails:**
  - Advisor escalation only with student consent, every time.
  - Consent is not a one-time blanket agreement; the student chooses what to share, and when.
  - Anonymised warning accuracy is reviewed by the advisor in Stage 2 (see `08-release-portfolio.md`) — anonymised means no student can be identified from it.

### 9. Over-reliance — students stop checking the original sources

- **What could go wrong:** Students trust the assistant completely and stop checking email, the LMS, or the notice board. If the assistant misses a deadline, no one catches it.
- **Who is harmed:** The student.
- **Guardrails:**
  - Tell students clearly: this is a helper, not a replacement for checking official sources.
  - Show the source of every deadline, so the student knows where it came from.
  - Measure the missed-deadline rate in the pilot against the baseline — if it does not fall, pause and investigate.

## Guardrails summary

| Guardrail | Which risk it addresses |
|---|---|
| Student confirms every extraction before saving | 4, 6, 7 |
| Show the arithmetic + "based on X of Y classes recorded" on every attendance figure | 2, 5 |
| Student-only data store; one-tap delete of all data | 1 |
| Advisor escalation only with student consent | 1, 8 |
| Max one digest per week | 3 |
| Show the source of every deadline | 4, 9 |
| Ask the student when a date is ambiguous; do not guess | 6 |
| Show both versions when announcements conflict | 7 |

## Incidents — what to do if a guardrail fails

1. Stop the affected part of the system (pause, do not continue and hope).
2. Tell the affected students plainly what happened and what you are doing about it.
3. Record the incident here: date, what happened, who was affected, what you changed.
4. Do not restart until the fix has been tested.

| Date | Incident | Who was affected | Fix |
|---|---|---|---|
| TBD | TBD | TBD | TBD |
