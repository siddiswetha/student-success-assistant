# 05 — Metrics Plan (Task Success, Quality, Cost per Success, Harm)

## How to read this plan

Every metric below has a definition, a target where one is set, and a place to record the real result. Do not fill in results before you have measured them.

## 1. Task success — did the student complete the task?

| Metric | Definition | Target | Result |
|---|---|---|---|
| Extraction confirmed and saved | % of documents where the student confirmed (or corrected then confirmed) the extraction and it was saved | TBD in pilot | TBD |
| Deadline found in time | % of deadlines saved at least 3 days before the deadline (define "in time" before the pilot) | TBD | TBD |
| Weekly digest received | % of enrolled students who received the digest each week | 100% of enrolled | TBD |
| Attendance viewed | % of students who viewed their attendance at least once per week | TBD | TBD |

## 2. Quality — was the output correct and useful?

| Metric | Definition | Target | Result |
|---|---|---|---|
| Deadline extraction accuracy (pre-confirmation) | Correct deadlines / all documents, before the student corrects anything | Measure; improve | TBD |
| Deadline extraction accuracy (post-confirmation) | Correct deadlines / all documents, after student confirmation | ≥98% | TBD |
| Warning precision | Correct warnings / all warnings. A warning is "correct" if the student was genuinely at risk (below, or about to fall below, the threshold) and the warning arrived in time to act. | ≥90% in Stage 2 | TBD |
| Warning recall (missed warnings) | At-risk students who received no warning / all at-risk students. A missed warning is as serious as a wrong one. | Measure; aim for 0 missed | TBD |
| Attendance arithmetic accuracy | Correct calculations / all calculations checked by hand | 100% | TBD |
| Digest usefulness | % of students who say the digest helped them act (survey, Stage 2) | TBD | TBD |

**Warning precision — worked definition (EXAMPLE):**
> EXAMPLE: If the system sends 20 warnings and 18 were correct and timely, warning precision = 18 ÷ 20 = 90%.

## 3. Cost per success — what did each good outcome cost?

| Metric | Definition | Result |
|---|---|---|
| Cost per document extraction | Cost of one extraction (see `06-cost-latency.md`) | TBD |
| Cost per student per month | Total pilot cost ÷ students ÷ months | TBD |
| Cost per correct warning | Total cost ÷ number of correct, timely warnings | TBD |
| Cost per missed deadline avoided | Total cost ÷ number of deadlines students say they would otherwise have missed (self-reported, pilot survey) | TBD |

Cost per success matters more than total cost. A cheap system that warns wrongly is not good value. A slightly more expensive system that warns correctly, in time, may be.

## 4. Harm — what could go wrong, and did it?

| Metric | Definition | Target | Result |
|---|---|---|---|
| Missed-deadline rate (pilot vs baseline) | Missed deadlines per student during the pilot, compared with the self-reported baseline before the pilot | Lower than baseline | TBD |
| False reassurance cases | Times the system said (or implied) "you're fine" when attendance data was incomplete or wrong | 0 | TBD |
| Wrong-deadline incidents | Times a wrong deadline was saved (even after confirmation) and affected a student | 0 | TBD |
| Alert fatigue | % of students who stop opening the digest, or ask to turn it off | Measure; investigate if rising | TBD |
| Privacy incidents | Times student data was shared without consent, or could not be deleted on request | 0 | TBD |
| Digest open rate | % of students who open the weekly digest | TBD | TBD |
| Digest action rate | % of students who take the suggested action (self-reported or observed) | TBD | TBD |

## Baseline — measure before the pilot

Before Stage 2, ask each pilot student:

1. How many deadlines did you miss last semester? (Self-reported baseline.)
2. How do you currently track deadlines and attendance?
3. How often do you discover an attendance problem too late?

Record the baseline here. Without it, you cannot show whether the pilot improved anything.

| Baseline question | Result (pilot cohort) |
|---|---|
| Missed deadlines last semester (per student, self-reported) | TBD |
| Students who track deadlines in one place | TBD |
| Students who knew their attendance % before the pilot | TBD |

## How often to measure

| Metric | When |
|---|---|
| Extraction accuracy | Every eval run; weekly during Stage 2 |
| Warning precision | Weekly during Stage 2 (advisor reviews anonymised warnings) |
| Attendance arithmetic | Every change to the calculation; full 10-case audit each time |
| Digest open + action rate | Weekly |
| Cost per student per month | Monthly |
| Harm metrics | Weekly during the pilot; immediately if an incident occurs |

## What "good" looks like at the end of the pilot

- Deadline accuracy ≥98% after confirmation, with 0 wrong deadlines saved.
- Warning precision ≥90%.
- Missed-deadline rate lower than the self-reported baseline.
- No false reassurance and no privacy incidents.
- Students open the digest and act on it — and do not ask to turn it off.
