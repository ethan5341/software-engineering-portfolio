Week 7 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------

---------------------------------------------------
Task 1 — Compare the Measures (50 min)
Q1.) A system was built twice: once in assembly (5,000 lines, 28 person-weeks) and once in a high-level
language (1,500 lines, 20 person-weeks). Compute the LOC/month productivity figure for each

- Assembly Language:
  - Lines of Code (LOC): 5,000 lines
  - Effort: 28 person-weeks / 4 weeks/month = 7 person months
  - Productivity: 5,000 LOC / 7 person-months = 714.29 LOC/month

- High-Level Language:
  - Lines of Code (LOC): 1,500 lines
  - Effort: 20 person-weeks / 4 weeks/month = 5 person-months
  - Productivity: 1,500 LOC / 5 person-months = 300.00 LOC/month


Q2.) By LOC/month, which approach 'wins'? Now compare total delivery time and effort instead — which
approach actually delivered faster and cheaper?
By LOC/month, the Assembly language method wins with 714.29 LOC/month compared to 300 LOC/month with the High-Level Language method.

- Comparison:
  - Faster: The High-Level Language method delivered much faster, with it only needing
  20 person-weeks compared to Assembly's approach of 28 person-weeks, saving 8 weeks of time-to-market.

  - Cheaper: The High-Level Language method is much cheaper due software engineering costs
  being driven by labor time in person-weeks, which reduces the effort from 28 weeks to 20 weeks. It directly translates approxiamtely
  28.5% reduction in total development cost.

The Assembly team generated more lines of code per month because low-level programming requires larger amounts 
of verbose code to handle basic operations and functions. While the High-Level approach was more efficient due to 
the language allowing them to reach the same level of function with 70% fewer lines of code, resulting in a faster and cheaper release.


Q3.) A small project is estimated at 197 function points. If programmers average 18 function points per
month and cost €5,200 per person-month, compute the estimated duration and labour cost

The estimated duration is 10.94 months and the total estimated labor cost is €56,911.11.

- Estimated Duration (Person-Months):
197 Function Points / 18 FP/month = 10.94 months}

- Estimated Labour Cost:
10.9444 person-months * €5,200/month =€56,911.11


Q4.) Explain in 2-3 sentences why LOC and function points can point to different conclusions about the same
project

Lines of Code measures the physical volume of a solution, while Function Points measure the functional 
value delivered to the user despite language the team used. 
A project with high-level language will have a lower LOC count despite producing high functional value, which makes it seem unproductive 
because it is under LOC metrics but highly efficient under FP metrics. This the metrics to diverge and change path, 
as LOC penalizes efficient programming while FP reflects the production of system capabilities.

---------------------------------------------------

---------------------------------------------------
Task 2 — Where Would This Mislead a Manager? (40 min)
Q1.) Using this week's safeguards (same language, no code-padding, comparable complexity/experience,
accounting for process quality, project size and working environment), decide whether it's ever safe to
use a raw LOC/month figure to compare two individual developers in a performance review.

No, it is not safe to use raw LOC/month figures to compare performance even with safeguard in place. 
While safeguards reduce macro-level variables like language differences and code-padding, 
raw volume is still inaccurate for performance due to micro-level realities of software engineering:

- Good Design Penalty: Highly skilled developers will long periods of time refactoring problems down to a clean solution.
While a less experienced developer may write 100-line nested loop to solve the exact same problem.
Using raw LOC figures would penalize the skilled engineer for being more concise and efficient.

- Task Profiles: Within the same project and language, one developer may be assigned to a
complex integration where they many hours debugging or writing logic that produces few lines of code.
Another develiper might be assigned to build UI templates that generate thousands of lines of code very quickly.

- Non-Coding Value: Software engineering involves non-coding contributions that
a raw LOC metric removes. It fails to capture time spent on design, code reviews, writing tests, or fixing system bugs.


Using raw LOC/month to measure performance creates an inaccurate incentive structure. 
If developers know they are judged on volume, they would choose verbose code writing compared to 
simple architecture, prolonging maintainability and system quality.

Q2.) Write a short memo (150-200 words) to a manager explaining what productivity data IS safe to use for
(team-level estimation, tracking trends over time) versus what it should NOT be used for (individual
reward or punishment), using today's assembly-vs-high-level example as your evidence

TO: Engineering Management
FROM: ATU Letterkenny Campus
DATE: 10/11/2026
SUBJECT: Application of Software Productivity Metrics

Productivity data must be applied only to institutional planning rather than developer evaluations and performance reviews.

Function Points and historical effort loops are safe and effective for developer estimation and 
tracking process trends while they work. It establishes baselines and budget project timelines accurately, 
while also identifying potential bottlenecks in the development environment.

Additionally, productivity metrics should not be used for performance ratings. 
Quantitative volume has many issues for human performance. This was showcased earlierm, with the assembly language method
producing 714 LOC/month, while the high-level language method produced only 300 LOC/month. Despite the lower number, 
the high-level team delivered the same amount of functional points to the system eight weeks faster and significantly cheaper.

Reviewing engineers based on raw code output creates a poor incentive enviroment. Developers will aim to create complex and 
diluded code over simple and less complex approaches in order to gain performance ratings, which in turn, 
reduces software maintainability. They must be rewardard on code quality, and functional delivery rather than raw volume.

---------------------------------------------------

---------------------------------------------------
Task 3 — Portfolio entry (30 min)
Q1.) Commit your calculations and memo to your GitHub portfolio under week07/

---------------------------------------------------

-----------------------------------------------------------------------------------------------------


