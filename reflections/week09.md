Week 9 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------

---------------------------------------------------
Task 1 — Build a GQM plan (60 min)
Q1.) Work through this task individually (your lecturer may instead ask you to pair up — follow whatever
they say on the day).

Q2.) Select one assigned goal.

I chose Goal Scenario B: Improve Code Maintainability. 

Q3.) Write the goal using Basili's three templates: purpose, perspective and environment (state it as a
percentage change from a baseline if you can).

- Purpose: Analyze and improve the maintainability of the existing production codebase—specifically targeting a 25% reduction in average
feature implementation cycle time and a 20% reduction in new developer onboarding time compared to the current Q0 baseline—over the
next two quarters.

- Perspective: From the viewpoint of the development team (focusing on daily ease of modifying code, confidence when
changing legacy modules, and onboarding speed).

- Environment: Within the team's active production codebase, version control repositories (Git), CI/CD pipelines,
and issue-tracking system.


Q4.) Derive at least 3 questions from the goal that must be answered to know whether it is being met.

- Question 1 : Is the codebase becoming structurally simpler and less risky ("scary") to modify?
- Question 2: Is the speed of implementing new features improving relative to code size?
- Question 3: Are new developers onboarding faster and gaining confidence in the codebase?

Q5.) For each question, derive at least one specific, collectible metric (one metric may answer more than one
question, as in the coding-standard tree).
Question 1: 
- M1: Average Cyclomatic Complexityof Modified Files: Mean McCabe cyclomatic complexity score of functions/methods within files touched during a sprint (collected via static analysis).
- M2: Lines of Code Changed per Feature: Total non-comment, non-blank source lines added, modified, or deleted per completed feature ticket (collected via Git diff logs).
- M3: Automated Branch Coverage on Modified Code: Percentage of executable branches in newly written or refactored code covered by automated unit/integration tests (collected via CI/CD test runner).

Question 2: 
- M4:Feature Implementation Effort (Hours): Total active engineering hours logged between a feature ticket moving to "In Progress" and its pull request (PR) being merged (collected via Jira/issue tracker & Git timestamps).
- M2: Lines of Code (LOC) Changed per Feature: (Shared with Q1) Used here to normalize implementation effort against the size of the feature.
- M5: PR Review & Rework Cycles: Number of review iterations (commits pushed after initial PR review) before approval (collected via GitHub/GitLab API).

Question 3: 
- M6: Time to First Merged Non-Trivial PR (Days): Calendar days from a new developer's start date until their first feature or bug-fix PR (excluding documentation/config-only changes) is merged into the main branch.
- M7: Developer Confidence Rating (1–5 Scale): Bi-weekly anonymous survey score answering: "How confident do you feel modifying core/legacy modules without causing unintended regressions?"
- M5: PR Review & Rework Cycles: (Shared with Q2) Tracked specifically for new hires during their first 60 days to measure onboarding friction.

Q6.) Say what model you would use to combine the metrics to answer each question (for example, effort per
LOC), and define any metric the tree leaves open.

- Q1 Structural Risk Score:
Risk Score = (M1 [Mean CC] * ln(M3 [SLOC])) / M2 [Branch Coverage %]
Evaluated alongside M7 (Confidence)—a falling risk score and rising confidence confirm safer code.

- Q2 Normalized Delivery Efficiency:
Effort per KLOC = M4 [Hours] / (M3 [SLOC] / 1000)
Rework Rate = Sum(M5 [Rework Cycles]) / Total Feature PRs
Normalizes implementation time by feature size (M3) while ensuring speed isn't causing review bottlenecks (M5).

- Q3 Onboarding Ramp-Up:
Onboarding Speed = Median(M6 [Days to First PR]) paired with New-Hire Mean(M5, M7) and M2 [Branch Coverage %]
Tracks ramp-up time (M6) alongside new-hire review friction (M5), confidence (M7), and test safety nets (M2).

- Metric Definitions
  - Logical SLOC: Added + modified executable source lines per feature diff (excludes blanks, comments, and lockfiles).
  - Implementation Effort (M4): Active working hours (8h/business day) from "In Progress" to PR merge, excluding external blockers.
  - PR Rework Cycle: One round of commits pushed after a reviewer requests changes.
  - Non-Trivial PR: A merged PR changing at least 20 logical SLOC in production code with at least 1 automated test (excludes docs/configs).
  - Confidence Score: Mean score on a 1–5 Likert scale (1 = High fear of regressions to 5 = Safe to refactor).


---------------------------------------------------


---------------------------------------------------
Task 2 — Plan the measurement process (30 min)
Q1.) For each question, state a hypothesis: what do you expect the data to show, and why?

- Q1 Hypothesis Structural Risk: Over the next two quarters, the Structural Risk Score will decrease by at least 25%,
while Developer Confidence (M7) will rise above 3.8 / 5.0. Why: Refactoring high-churn legacy modules and enforcing branch
coverage on touched files will break up tightly coupled logic and give developers an automated safety net.

- Q2 Hypothesis Feature Speed: Effort per KLOC will drop by 25% from the Q0 baseline, and the Rework Rate (M5) will
fall below 1.5 cycles per PR. Why: Clearer, decoupled module boundaries reduce the cognitive load needed to understand
existing code and prevent unexpected side effects during code review.

- Q3 Hypothesis Onboarding & Safety: Median Time to First Non-Trivial PR (M6) will decrease by 20%, and new-hire rework
cycles will match tenured team averages within 45 days. Why: Higher test coverage (M2) and simpler module structures
allow new hires to make changes safely without relying on tribal knowledge.


Q2.) For each metric, write a precise definition of what is counted and what is not (as you would for a line of
code).
- M1 Cyclomatic Complexity: Count branching keywords (if, else if, for, while, case, catch, &&, ||) plus 1 in modified production functions.
Exclude test files, vendor libraries, generated code, and untouched files.

- M2 Branch Coverage %: Count the percentage of executable if/else and switch branches in modified production files
hit by automated CI tests. Exclude manual QA, UI snapshots, config files, and annotated dead code.

- M3 Logical SLOC Changed: Count added or modified executable statements in production files per feature branch diff
against main. Exclude blanks, comments, deleted lines, lockfiles, and markdown docs.

- M4 Feature Effort: Count active business hours (8h/weekday) from "In Progress" to PR merge. Exclude weekends, holidays,
"Blocked" status time, and non-feature tickets.

- M5 PR Rework Cycles: Count rounds of new commits pushed after a reviewer requests changes.
Exclude pre-review commits, automated CI formatting, and main merge-conflict updates.

- M6 Time to First Non-Trivial PR: Count calendar days from a new hire's start date until their first merged
PR with >= 20 logical SLOC and >= 1 test. Exclude docs-only, README, setup, or reverted PRs.

- M7 Confidence Score: Count anonymous 1–5 Likert responses from full-time developers on the bi-weekly survey.
Exclude manager responses, incomplete entries, and ad-hoc feedback.

Q3.) Write a short procedure for collecting and reporting the data, and say how you would validate it.
CI pipelines automatically log M1, M2, and M3 on every PR, while sprint-end scripts pull M4, M5, and M6 from Jira and Git APIs, 
and a Slack bot collects M7 bi-weekly. Data feeds a team-level Sprint Maintainability Dashboard reviewed during Sprint 
Retrospectives (never tracked per individual to avoid gaming). To validate accuracy, the team lead manually audits five 
random PRs against raw Git and Jira logs in Sprint 1, enforces an 80% minimum response rate for M7, and checks Jira "Blocked" 
tags during stand-ups.

Q4.) Say which trend over time you would look for, rather than relying on a single data point.
nstead of reacting to single-sprint outliers, the team will track a rolling 3-sprint moving average for M1, M2, Effort 
per KLOC, and M5 to smooth out variations in feature difficulty. For onboarding and sentiment, the team will compare Q1/Q2 
new-hire cohorts for M6 against the Q0 baseline and monitor the upward linear slope of M7 across all 12 sprints to ensure sustained developer confidence.

Q5.) Start small: choose a basic set of initial metrics to measure first, and explain why.
In Month 1, the team will start with just three metrics: M3 (Logical SLOC), M4 (Feature Effort), and M7 (Confidence). 
M3 and M4 require zero setup because they already exist in Git and Jira history (establishing an immediate Effort per KLOC baseline), 
while M7 takes minutes to launch via a poll—giving an instant balance of delivery speed and developer sentiment before configuring 
heavier CI tools (M1, M2).
---------------------------------------------------

---------------------------------------------------
Task 3 — Peer review (30 min)
Q1.) Swap plans with a classmate.

Q2.) Review against the lecture: does each metric genuinely answer its question? Does the goal relate to a
real organisational problem, and is anything missing or ungrounded in it?
- Organisational Problem & Goal: The goal directly addresses a real organisational bottleneck—slowing feature delivery,
rising onboarding times, and fragile legacy modules ("scary" code)—framed properly using Basili’s Purpose, Perspective,
and Environment with percentage targets over two quarters. Nothing core is ungrounded, though the Q0 baseline figures must
be captured in Week 1 before the percentage targets can be locked in.

- Question-Metric Alignment: Every metric genuinely maps to its question. Structural risk (Q1) is covered by Cyclomatic
Complexity (M1) and Branch Coverage (M2); delivery speed (Q2) is covered by Effort (M4) normalized by SLOC (M3); and
onboarding safety (Q3) is covered by Time to First PR (M6) and Developer Confidence (M7). Sharing M2, M3, and M5 across
questions effectively links code structure to team velocity.

Q3.) Is there a model to combine the metrics, and is every metric precisely defined so that two people would
count it the same way?
- Combination Models: Each question has an explicit mathematical or analytical combination model (Structural Risk Score for Q1,
Effort per KLOC and Rework Rate for Q2, and Median Onboarding Time paired with new-hire rework/confidence for Q3) rather than
relying on isolated raw numbers.

- Counting Precision (Reproducibility): Every metric defines exact inclusion and exclusion boundaries—such as counting
logical SLOC while excluding blanks, comments, and lockfiles, and excluding weekends and external blockers from active effort
hours—so two different engineers auditing the same PR would calculate the exact same values.

Q4.) Is there a risk of dysfunctional measurement (for example, measuring productivity but not quality)? Is
the plan small enough to start with?
- Dysfunctional Measurement Risk: Tracking Effort per KLOC carries a minor risk of incentivizing verbose code or rushed PRs
if viewed in isolation. However, this is well-mitigated by reporting strictly at the team level (never individual developer rankings)
and pairing speed metrics with quality guardrails (Branch Coverage M2 and PR Rework Cycles M5).

- Starting Small: Starting in Month 1 with just three metrics (M3 Logical SLOC, M4 Feature Effort, and M7 Developer Confidence)
is small and practical enough to launch immediately using existing Git/Jira logs and a quick pulse poll without heavy CI tooling delays.

Q5.) Provide written feedback, then commit your final plan and the feedback you received to GitHub under
week09/
Strong GQM alignment and clear mathematical models—especially normalizing effort by KLOC and using a 3-sprint moving 
average to avoid single-sprint noise. To make sure no gaming occurs around SLOC or cycle time, keep all dashboards 
strictly team-aggregated and enforce your test coverage and rework guardrails during retrospectives.

---------------------------------------------------

-----------------------------------------------------------------------------------------------------
