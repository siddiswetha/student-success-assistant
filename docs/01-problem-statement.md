# 01 — Problem Statement with Evidence

## The problem

Universities lose students not only to academic difficulty but to missed deadlines, fragmented communication, and attendance shortfalls discovered too late.

Deadlines are announced in many places: in class, by email, on the LMS, and on notice boards. No single channel holds everything. A student who misses one announcement can miss a deadline entirely.

Attendance is a quieter risk. A student may fall below a requirement — for example, 75% — without realising it, and only learn about it when there is no recovery path left. At that point, advice such as "attend more classes" is no longer useful.

## Who has this problem

- **Students**, especially first-year students and students juggling work, commuting, or family responsibilities. They need one clear view of what is due and where they stand.
- **Academic advisors and tutors**, who want to help early, but often only see a problem after a deadline has passed or attendance has already fallen too far.
- **Universities**, which lose students who could have succeeded with an earlier warning.

## Why now

Communication is more fragmented than before, not less. A notice can appear in any one of several systems, and students are expected to check all of them. At the same time, attendance rules are strict and unforgiving: a small shortfall, discovered late, can have a large consequence.

Early, accurate warning gives students and advisors time to act. A wrong warning, or a missed one, destroys trust in the system — so accuracy matters as much as speed.

## What "good" looks like

A student can answer, in under a minute:

1. What is due this week, and when exactly?
2. What is my attendance in each subject, and how is it calculated?
3. Which subjects are at risk, and what is the one action I should take next?

An advisor, with the student's consent, can see the same at-risk picture and offer help before the deadline or the attendance threshold passes.

## What this project will not do

- It will not submit assignments automatically.
- It will not contact faculty on the student's behalf.
- It will not predict grades.

Those limits are deliberate. They keep the student in control and keep the system honest about what it can and cannot know.

## Evidence to collect (do not assume)

Before building anything, collect real evidence for each claim below. Record the source, date, and number of people or cases behind each point. Leave a row blank if you have not collected it yet.

| Claim | Evidence needed | Source / date | Result |
|---|---|---|---|
| Deadlines are announced in more than one channel | Channel map from research (see `02-research-notes.md`) | TBD | TBD |
| Students have missed a deadline because they did not see the announcement | Interview answers from at least 5 students | TBD | TBD |
| Attendance is discovered too late to recover | Interview answers; advisor interview | TBD | TBD |
| How attendance is calculated in your institution | Written rule from the institution — do not assume | TBD | TBD |
| The attendance threshold (e.g. 75%) and what happens below it | Written rule from the institution | TBD | TBD |
| A wrong or late warning damages trust | Interview answers; pilot feedback | TBD | TBD |

## Success criteria

This project succeeds if:

- Deadline extraction is ≥98% accurate after human confirmation.
- Attendance arithmetic is 100% correct on the audit (10 cases checked by hand).
- At-risk warnings are correct and timely — measured as warning precision in the pilot.
- Students act on the weekly digest, rather than ignoring it.

## Risks if we do nothing

Students continue to miss deadlines they could have met, discover attendance problems too late, and lose trust in any system that warns them incorrectly. Advisors continue to find out too late to help.
