Week 8 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------

---------------------------------------------------
Task 1 — Pick an Attribute and an App (45 min)
Q1.) Choose one external attribute: reliability, maintainability, or usability.
Maintainability.

Q2.) Choose an application you use regularly.
Microsoft Outlook.

Q3.) Propose two concrete measurements you could realistically take for that attribute, drawing on this
week's named metrics (e.g., a SUS score and time-on-task for usability; MTTR and % of changes
introducing new faults for maintainability; POFOD or AVAIL for reliability).

- Mean Time to Repair (MTTR): This measures the average time it takes for Microsoft to release an update
after a known bug is acknowledged in Outlook. A lower MTTR dictates that the code is
modular and easy for engineers to diagnose and fix bugs quickly.

- Percentage of Changes With New Faults (Change Failure Rate): This measures the amount
of scheduled Outlook client updatesthat introduce a new regression, error or break ofo an existing feature
that was working previously. A low percentage shows that changes are isolated and do not cause
unintended or widespread side effects across other sections of the application.

Q4.) Describe exactly how you would collect each measurement and over what period.

- Collecting Mean Time to Repair (MTTR)
Track Microsoft 365 Admin Center Service Health dashboard, Microsoft Outlook
Release Notes page, and the Microsoft Tech Community bug-tracking forums.

  - Collection:
	1. Log the date and timestamp when Microsoft acknowledges a new bug.
	2. Monitor patch notes until a build number is released with a confirmed fix for that bug.
	3. Calculate the time between the acknowledgment timestamp and the patch release timestamp.
	4. Calculate the Average for these times durations across all tracked bugs.
  
  - Collection Period: 3 months. This timeframe gives provides enough update cycles to
  capture multiple issues of different scales from discovery to resolution.


- Collecting Percentage of Changes Introducing New Faults

  Monitor the Microsoft Learn Outlook Update History page, user reported threads, and Microsoft Q&A after each version rollout.

  - Collection:
	1. Record every update pushed to the Outlook update channel.
	2. Following each update, track whether Microsoft issues a known issue report for that build or creates a hotfix. 
	3. Divide the number of updates that caused a new fault by the total number of updates released during that timeframe and multiply by 100.

  - Collection Period: 6 months. Due to major updates happening monthly, a six-month window has about 12-18 update events, allowing for a larger sample size.

---------------------------------------------------

---------------------------------------------------
Task 2 — Critique Your Own Approach (45 min)
Q1.) Identify one way your chosen measurement could be gamed, misleading, or simply wrong.

- Delayed Acknowledgment: Microsoft controls when a bug or problem is 
added to the a known issues list. Engineers may investigate and try to fix bugs long before they arepublicly
acknowleged, which reduces MTTR.

- Unfinished Repairs: Microsoft marks an incident as resolved by publishing a temporary registry edit or
telling users to revert to older versions. Considering a workaround as a repair hides the fact that the issue
is still there.

- Incorrect Reporting: Major issues are publicaly documented,
while minor bugs fixed quickly and cleanly in general updates without appearing on a
dashboard. Relying only on public advisories skews the data toward high severity bugs rather
than representing the overall codebase maintainability.

Q2.) Propose one concrete change that would make the measurement more trustworthy.

- User Reports: Instead of starting the timer when
Microsoft acknowledges a bug, start the clock at the timestamp of the first 
bug us report, and match that to the that official fix. This prevents reporting delays
from hiding the diagnosis time.

- Verified Code Patch to Stop the Clock: Only stop the MTTR timer when Microsoft deploys
an update that resolves the issue without requiring user intervention. Exclude
workarounds or version rollbacks from stopping the clock, ensuring the metric only measures maintainability.
---------------------------------------------------

---------------------------------------------------
Task 3 — Portfolio entry (30 min)
Q1.) Commit your proposal and critique to your GitHub portfolio under week08/.
---------------------------------------------------

-----------------------------------------------------------------------------------------------------
