# Business School Performance Analytics & Retention Strategy

[![Power BI Dashboard](https://img.shields.io/badge/Power%20BI-View_Dashboard-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiNmQ4MzMzYzQtYWUyYi00ZTcyLTg4MDEtZThlNDE2N2YzNjBkIiwidCI6IjgyYzUxNGMxLWE3MTctNDA4Ny1iZTA2LWQ0MGQyMDcwYWQ1MiJ9&pageName=8d3b53fb6270bcb04f5e)
[![Case Study](https://img.shields.io/badge/Case_Study-Read_the_page-111111?style=for-the-badge)](https://racheltran184.github.io/PowerBI-Project-1/)

**Two in three leavers are visible by mid-year.** Five years of Macquarie Business School data (284,741 unit enrolments for 21,824 bachelor students) built into a Power BI dashboard, then re-analysed to find who leaves, when it shows, and which action would keep them.

---

## Overview

The Business School asked for one view of five years of bachelor enrolments: *is retention recovering, and where should support go?* The dashboard answers the first half for executives, course directors and unit convenors. The re-analysis answers the second. It rebuilds the data one student-year at a time, session by session, so every finding comes with a trigger, a date and a headcount, and every action names an owner.

| Item | Detail |
|---|---|
| **Client** | Macquarie Business School, with the University's Business Intelligence & Reporting team |
| **Data** | 284,741 unit enrolments and 52,430 retention records, 2020 to Session 1 2025, de-identified |
| **Scope** | 21,824 bachelor students in 85 Business School courses, across 1,014 units |
| **Tools** | Snowflake (star schema), Power BI (five pages), Python (pandas, scikit-learn) |
| **Origin** | BUSA8031 group project, Macquarie University (Group 17); re-analysed in depth for the case study |

### Headline numbers

| Figure | What it means |
|---:|---|
| **89.6%** | University retention in 2024, up from 85.0% in 2022 |
| **74%** | Share of 2024's leavers who studied part-time; part-timers were 35% of students |
| **64%** | Share of 2024's leavers flagged by four mid-year signals, which flagged 22% of students |
| **52%** | Part-timers who took Session 1, skipped Session 2 and didn't return (315 of 601 in 2024) |
| **68%** | Fails in the six big first-year units that were no-shows (fail-absent) in 2024 |

---

## What changed when I went deeper

The first version of this project reported averages, flagged segments by rate, and recommended programs without saying how many students each would reach. The re-analysis tested each claim.

| Question | First version | Re-analysis | Verdict |
|---|---|---|---|
| Is retention recovering? | Recovered to 90% in 2024 | Yes: 85.0% in 2022 to 89.6% in 2024, but part-timers retain at only 78.1% | Holds |
| Who leaves? | Single-degree, part-time, external students (76% retention) | Part-timers: 74% of 2024's leavers, 61% of them on campus. The named segment held 13% of leavers | Changed |
| When do they leave? | Not measured | After Session 1: half of part-timers who skip Session 2 don't return, and they are 46% of 2024's leavers | New |
| Gateway units | ACST1001, STAT1250 and MGMT1002 as high-risk units | Six first-year core units; in 2024, 68% of their fails were no-shows, so follow-up comes before tutoring | Sharper |
| Riskiest courses | Bachelor of Economics, 43.8% drop-out | 13.0% a year over 1,063 student-years; the 100% and 50% rates came from courses with one and four students in 2024 | Changed |
| Course portfolio | Consolidate the bottom 20 courses | The 47 courses with fewer than 20 student-years hold 0.3% of leavers: tidy them for admin reasons, not retention | Reframed |
| Predicting who leaves | XGBoost, 93.4% accuracy | Predicting "stays" for everyone scores 89.6%. A point-in-time model tested on 2024 catches 71% of leavers from 22% of students | Changed |
| What drives risk | Behaviour, not demographics | Session 2 load, Session 1 fails and being a new student lead; nationality, age and study mode add little | Holds |

---

## Six findings

### 1. The recovery is real, but part-timers lag
University retention fell from 90.5% in 2020 to 85.0% in 2022, then recovered to 89.6% in 2024. About 40% of the 2022 fall came from mix: continuing domestic part-timers, a group where three in ten leave, grew from 15.5% to 20.5% of students. The rest came from higher leaving rates, most sharply among international students, whose rate doubled from 7.4% to 14.7%. In 2024, part-timers retained 78.1% against 95.8% for full-timers. Over five years they were 36% of students and 73% of leavers.

### 2. Leavers are mostly part-timers, and most are on campus
In 2024, continuing part-timers were 18% of students and 46% of leavers; a quarter of them left. New part-timers added another 28% of leavers. The single-degree, part-time, external segment the first version flagged held 13% of leavers, while 61% of part-time leavers studied on campus. Part-time study, not online study, is the risk to manage.

### 3. Most leaving shows by the Session 2 census

| Signal (2020–2024) | Student-years | Left by the next year |
|---|---:|---:|
| Part-timer took Session 1 but didn't enrol in Session 2 | 3,535 | 51.0% |
| Fail-absent grade in Session 1 | 2,691 | 38.4% |
| New student failed or withdrew from a first-year core unit in Session 1 | 2,606 | 28.7% |
| Dropped from full-time to part-time | 2,800 | 22.5% |
| All student-years | 34,756 | 11.9% |

In 2024, the four signals flagged 1,455 students (22%), who included 437 of the 685 leavers (64%). The other 5,152 students lost 4.8%. The University already holds this list months before the official rate records the loss.

### 4. In the big first-year units, most fails are no-shows
In ECON1020, ACCG1000, ACST1001, MGMT1002, STAT1250 and MKTG1001, 783 of 1,153 fails in 2024 (68%) were fail-absent: students who stopped submitting or sitting assessments, not students who tried and failed. The damage compounds. New students who failed or withdrew from one of the six left at 17.3%, two at 26.7% and three or more at 38.4%, against 7.2% for those who passed every one they took. Tutoring reaches students who turn up, so the first fix is following up the first missed assessment.

### 5. Course alarms were small-sample noise
Across the 15 courses with at least 500 student-years, the yearly leaving rate runs from 5.4% to 15.2%. The Bachelor of Economics loses 13.0%, not 43.8%. The dashboard's 100% and 50% drop-out rates came from courses with one and four students in 2024, and 47 of 83 courses had fewer than 20 student-years in five years. Size matters more than rate: the Bachelor of Commerce is 43% of student-years and 45% of leavers. The Bachelor of Business has the highest rate (15.2%) with no more part-timers than Commerce (38.6% against 39.5%), so its cause sits inside the course.

### 6. A model only helps at a set capacity
Nine in ten students stay, so predicting "stays" for everyone is already 89.6% accurate. A point-in-time model trained on 2020–2022 and tested on 2024 catches 71% of leavers when it flags 22% of students, against 64% for the four signals; the top 10% catches half. The four signals are transparent and already capture most of the gain, so they come first. See [Predictive model](#predictive-model).

---

## Action plan: the next 12 months

Each action names the trigger, the students in scope and the measure. Sizes are 2024 headcounts; "kept" figures are arithmetic, not promises.

| # | Owner | Action | In scope (2024) | Measure |
|---|---|---|---|---|
| 01 | Student advisers | In August, call every part-timer who took Session 1 but has no Session 2 enrolment; offer a lighter load, leave or a Session 3 unit | 601 students; 315 didn't return (46% of all leavers). A 10-point cut keeps about 60 a year | Share re-enrolled by next Session 1 |
| 02 | Student advisers | Contact every student with a Session 1 fail-absent grade within five working days and agree a plan before the Session 2 census | 724 students; 35% left | Fail-absent students enrolled for Session 2 |
| 03 | Student advisers | When a full-time student re-enrols part-time, book a completion-planning call before census | 512 students; 22.5% leave after a load drop against 3.8% who stay full-time (2020–2024) | Completion plans agreed per load drop |
| 04 | Unit convenors | In weeks 3–6, flag students who miss the first assessment in the six core units and have their tutor follow up | 783 of 1,153 fails were fail-absent | Fail-absent rate per unit, each session |
| 05 | Unit convenors | Run peer-assisted study where students sit the work and still fail | MGMT1002 (136 attempted fails), ACST1001 (86), STAT1250 (72) | F-grade rate in those three units |
| 06 | Unit convenors | Re-enrol new students who fail or withdraw from one of the six in Session 1 into a supported repeat, with an adviser check-in | 313 students | Retention of supported-repeat students |
| 07 | Course directors | Pilot actions 01–03 in the Bachelor of Commerce, with the other large courses as the comparison | 45% of leavers (1,931 over 2020–2024) | Commerce retention against comparison courses |
| 08 | Course directors | Review the first-year sequence, timetable and part-time pathway of the Bachelor of Business | 15.2% leave each year, the most of any large course | Business retention, new and continuing |
| 09 | Course directors | At the end of first year, offer combined-degree students a credit-mapped move into one of their two degrees | 45% of combined-degree students who change course already pick one of their two halves | Planned switches against exits |
| 10 | Executives & BI | Add a monthly dashboard measure: Session 2 enrolment among Session 1 part-timers | 57.5% enrolled for Session 2 | Session 2 enrolment of Session 1 part-timers |
| 11 | Executives & BI | Size adviser capacity to the flagged list and contact students in random order over two weeks to measure the effect | About 1,450 students a year, holding 64% of leavers | Leavers per 100 flagged, early against late contact |
| 12 | Executives & BI | Report any risk model as the share of leavers in the top 15–20% it flags, tested on a later year | The model's top 20% held 69% of leavers | Leavers caught at capacity, each year |

---

## Three-year strategy

The 12-month actions test what works; the strategy builds it into how the School runs. Every 5-point cut in the flagged group's leaving rate keeps about 73 students a year, about one point of university retention.

| Track | Year 1 (now) | Year 2 (next) | Year 3 (later) |
|---|---|---|---|
| **Find them early**<br>BI team, student advisers | A weekly list of students who hit any mid-year signal, owned by the advising team | Add learning-platform logins and assessment submissions, the signal that comes before a fail-absent grade | Rank the list with the point-in-time model once it beats the rule on a new year |
| **Keep them enrolled**<br>Advisers, course directors | August calls to Session 1 part-timers, with load, leave and Session 3 options | Timetables, online sections and Session 3 units built for part-timers, starting in Commerce | Every continuing part-timer holds a dated plan to graduate, reviewed each year |
| **Fix the gateways**<br>Unit convenors, learning and teaching | Missed-assessment follow-up in weeks 3–6 of the six core units | Peer study in MGMT1002, ACST1001 and STAT1250 | Rework the assessment of any unit whose fail-absent rate stays above its peers |

**Leading measures, checked monthly:** Session 2 enrolment of Session 1 part-timers (57.5% in 2024) · fail-absent grades per 100 enrolments in the six units (9.5) · flagged students contacted within 10 days · load drops with a completion plan.

**Outcome measures, checked yearly:** university retention (89.6% in 2024) · part-time retention (78.1%) · leavers among flagged students (30.0%) · leavers caught when 20% are flagged (69%).

---

## Predictive model

| Item | Detail |
|---|---|
| **Unit** | One row per student per year, completers excluded: 34,756 student-years, 2020–2024 |
| **Features** | Only what is known by the Session 2 census: Session 1 units, fails, fail-absent grades, withdrawals and load; Session 1 results in the six core units; Session 2 enrolment and units; part-time, new student, international, study mode, combined degree, age, application path; prior-year fails, fail-absent grades, withdrawals and load |
| **Models** | Gradient boosting (scikit-learn `HistGradientBoostingClassifier`) and logistic regression |
| **Split** | Trained on 2020–2022, checked on 2023, tested on 2024 |
| **Judged by** | Leavers caught at a fixed capacity, not accuracy |

Results on 2024 (685 leavers among 6,607 students):

| Approach | Students flagged | Leavers caught | Share of leavers | Share of flagged who left |
|---|---:|---:|---:|---:|
| Model, top 10% | 661 | 346 | 50.5% | 52.3% |
| Model, top 15% | 991 | 423 | 61.8% | 42.7% |
| Model, top 20% | 1,321 | 470 | 68.6% | 35.6% |
| Model, top 22.0% | 1,455 | 484 | 70.7% | 33.3% |
| Four-signal rule | 1,455 | 437 | 63.8% | 30.0% |

AUC is 0.845 (logistic regression 0.835). The features that carry the most weight are Session 2 units, Session 1 fails, being a new student, Session 2 enrolment and part-time load.

**Why the first model was replaced.** The group project's XGBoost reported 93.4% accuracy, but predicting "stays" for everyone already scores 89.6%. Its top predictors included current WAM, which the data dictionary defines as the mark "as of today", so it is measured after the outcome it predicts. Its high-risk group held 8,675 students (39.7%), more than advisers could contact.

---

## Definitions

- **Retention:** retained in any Macquarie course the next year ÷ (enrolled − completers), the University's "new normal" method. Leavers are "not retained in year X + 1". 2025 has no outcome yet.
- **Fail-absent (FA):** a fail for not submitting an assessment task or not attending a required assessment.
- **Student-year:** one student in one academic year, with their session pattern, load change and fail types.

---

## Dashboard

| Page | For | Shows |
|---|---|---|
| Dashboard Summary | Everyone | Objectives, scope, structure and stakeholder navigation |
| University Overview | Executives | Retention, drop-out and fail rates with year, faculty, study mode and student filters |
| Course Performance | Course directors | Course retention, transfers and where students go when they leave a course |
| Unit Performance | Unit convenors | Pass, fail and withdrawal outcomes by unit and year, with a grade breakdown |
| What-Ifs | Executives | Effect and coverage sliders for three support programs. The effects are assumptions, so the action plan above sizes each action from groups the data can name |

---

## Tech stack

- **Snowflake:** star schema with enrolment and retention fact tables and student, course, unit, year, faculty and WAM dimensions.
- **Power BI:** five pages with drill-through from course to unit, stakeholder navigation and what-if parameters.
- **Python:** pandas for the student-year rebuild; scikit-learn for the point-in-time model. The group project's first model used XGBoost with SHAP.
- **Web:** a single self-contained `index.html` (vanilla JavaScript SVG charts, light and dark themes) served by GitHub Pages.

---

## Repository

| File | What it is |
|---|---|
| `index.html` | The case study page, served at [racheltran184.github.io/PowerBI-Project-1](https://racheltran184.github.io/PowerBI-Project-1/) |
| `Dashboard.pbix` | Power BI report |
| `Dashboard.pdf` | Static export of the dashboard |
| `LICENSE` | Apache License 2.0 |

---

## Data and privacy

Built on a de-identified dataset provided by Macquarie University for the BUSA8031 group project (Group 17). Only aggregate figures are reported: every rate rests on more than 100 students, and counts under 5 are suppressed. This is not an official Macquarie University publication.

---

**Rachel Tran** · [Portfolio](https://racheltran.vercel.app) · [LinkedIn](https://www.linkedin.com/in/racheltran184/) · [GitHub](https://github.com/racheltran184)
