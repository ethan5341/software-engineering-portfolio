Week 4 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------

---------------------------------------------------
Task 1 — Backlog, Sprint & Kanban Simulation (55 min)
Q1.) Review the PitchPerfect product backlog, T-shirt-size each story (S/M/L), and prioritise it.

- Must Have:
  - 1: Calendar of available pitch slots.
	Size: M.
	Rationale: Requires a clear and structural calendar layout with active database tracking.

  -  2: Pitch slot for a specific date and time.
	Size: M.
	Rationale: Requires transactional handling to manage overwritting and prevent double bookings.

  - 9: Daily booking schedule.
	Size: M.
	Rationale: Changes database entries into a viable dashboard to keep operations running continously.
  
- Should Have:
  - 3: Cancel a booking.
	Size: S.
	Rationale: Database state change to "= cancelled" to remove a booking.

  - 6: Pay for online booking.
	Size: L.
	Rationale: Requires setting up proper security measures, such as payment gateways, credential storage and error handling.

  - 8: Block pitch for maintenance.
	Size: S.
	Rationale: Basic override flag that prevents user booking pitch during a specified time.

  - 10: Filter slots by pitch size and surface type.
	Size: S.
	Rationale: Simple database query modification (size = x, surface = y).

  
- Could Have:
  - 4: Receive confirmation email.
	Size: S.
	Rationale: Setting up SMTP transactional microservice that automatically emails based on an event.

  -  5: See past bookings.
	Size: S.
	Rationale: History retrieval query pulling from database.

  - 7: Invite other players by link sharing. 
	Size: S.
	Rationale: Dynamic link generator that allows multple uses from different players.

  - 14: Export monthly bookings report.
	Size: M.
	Rationale: Requires file generation logic, such as CSV, to map to financial data structures.

  
- Won't Have:
  - 11: Reminder notification an hour before booking.
	Size: M.
	Rationale: Requires external SMS infrastructure.

  - 12: Peak and off-peak variable pricing models.
	Size: M.
	Rationale: Dynamic billing calculation logic inside checkout system.

  - 13: Rate pitch condition after playing.
	Size: S.
	Rationale: Review system survey added to the database.
  
   
Q.2) Set a WIP limit of 2 on your board's 'In Progress' column, select stories for a one-day 'sprint'
(representing a 2-week sprint in miniature), and set a sprint goal.
- WIP Limit: 2
- Rule: The teams can pull any new work into the "In Progress" section if there are already two items active in that column.
This displays any possible work bottlenecks and ensures the team finished the current workload before continuing.

- Sprint Goal: Establish a core booking lifecycle that allows users to view open slots, make reservations, and track their bookings.
- Sprint Backlog Stories (One-Day Scope):
Story 1 (Medium): See calendar of available pitch slots.
Story 2 (Medium): Book a specific date and time slot.
Story 9 (Medium): Daily booking schedule.

Product Backlog	- Ready (To Do)	
• Story 3 (S)     Story 9 (M)
• Story 6 (L)
• Story 8 (S)
• Story 10 (S)

In Progress - Done
Story 1 (M)   (Empty at start)
Story 2 (M)


Q3.) Move stories across your board as you 'complete' them; at the midpoint, write yourself a 2-minute
mock daily-scrum update (what's done, what's next, any blockers).
- Board Midpoint Status:
To Do:
Story 9 (M): Manager daily schedule.

In Progress:
Story 2 (M): Book a specific slot.	

Done:
Story 1 (M): View slot calendar.

  
- Scrum Update:
  - What was done since last Scrum?:
    The database scheme was completed and the logic layout for the calendar view was created. It has not been integrated into the main branch and demonstrates the product owner. 

  - What I will do next?:
    Next, I will move to story 2 and handle the transacitonal logic that allows users to book specific time slots from the calendar.

  - Any Blockers?:
    As of now, there are no blockers but I must communicate with the database manager to ensure the locking mechanism prevents 2 or more players from having the same booking. 

Q4.) At the end, briefly demo the completed stories to a nearby classmate as stakeholder, and hold a 2-
minute personal retrospective (what went well, what didn't, one action for next time)
- What went well:
The print scope was kept small, which allowed us to finish the  'Must-Have' features on time.
Additionally, using a strict WIP limit ensured that we finished the calendar view database queries before writing any other code, which helped the integration process.

- What didn't go well:
Too much time was spent structuring the grid layout for the calendar UI, which delayed our backend coding.
Handling race conditions to prevent double-bookings required extra technical complexity.

- One action for next time:
Next time, we will use a lightweight UI library for the layouts so we can focus more on our backend database validation and other core software logic.
---------------------------------------------------

---------------------------------------------------
Task 2 — Writing User Stories (40 min)
Q1.) Write at least 6 user stories in the format 'As a [role], I want [goal], so that [benefit]', covering at least
two different roles.
- User Story 1: As a student, I want to view my weekly timetable, so that I know when and where my classes are held.
- User Story 2: As a student, I want to see the room number and module details for each class, so I can understand where my class is and what it will cover.
- User Story 3: As a student, I want to change to a different class slot when they are at the same time, so that I can resolve any scheduling conflicts.
- User Story 4: As a student, I want to export my timetable to my phone, so that I can manage my schedule from a single, personal device.
- User Story 5: As a lecturer, I want to mark a specific class as cancelled or relocated, so that my students are immediately aware of schedule changes.
- User Story 6: As an administrator, I want to view which timetable slots are currently over capacity, so that I can allocate larger or different rooms to accomodate.

Q2.) Add acceptance criteria to two of your stories.
- Criteria for Story 3:
  - AC 1: The system must display lists of all alternative tutorial or lab sessions running for that module.
  - AC 2: A student must be blocked from swapping a slot if that session has maximum room capacity.
  - AC 3: The swap must be rejected and flag an error if the time slot has another clash with another class.

- Criteria for Story 5:
  - AC 1: A lecturer must only be permitted to modify classes that are assigned to their unique staff code.
  - AC 2: When a cancellation or relocation is saved, the system must notify students quickly.
  - AC 3: Relocating a class must dynamically check room availability to ensure the new room is empty.
   
Q3.) Swap with another classmate and peer-review: are the stories independent, negotiable, valuable,
estimable, small, testable (INVEST)?
- User Story 1 (Independent): The stories are segmented from one another and the calendar view can be built completely separately from the calendar export from Story 4 without breaking the pipeline.
- User Story 2 (Negotiable): Stories are starting points rather than rigid specifications, such a story 3 leaves room for negotiation during planning regarding swapping requiring manual or automatic approval 
- User Story 3 (Valuable):Each story delivers a clear business benefit to the user as students directly save time, and administrators can explicitly prevent overcrowding.
- User Story 4 (Estimable):Story 5 combines "cancelled" and "relocated" actions, which would mean the team should split these because building a cancellation flag requires very different backendthan booking. 
- User Story 5 (Small):The stories are scoped well as they can segmented into smaller tasks allowing them to fit into a smaller sprint type. 
- User Story 6 (Testable):The detailed acceptance criteria means these stories are highly testable as it allows a QA engineer to write automated and verifiable test parameters to verify room capacity limits and be notified.
---------------------------------------------------

---------------------------------------------------
Task 3 — Connecting an Engineering Practice, and Portfolio (25 min)
Q1.) Pick one XP practice — TDD, Continuous Integration, Pair Programming, or Refactoring — from this
week's reference handout

Q2.) Do a quick search for one real-world example or reported experience of a team using it
- Option C: Pair Programming:

- The Roles: The driver writes the code and focuses on the more immediate mechanics of a system, while the navigator reviews the code and focues more on design and tracks bugs or errors.
  
Positive: It has been stated that there is a signficant reduction in errors or bugs being either caught or prevented before a system is completed when someone one reviews the code. 

Negatives: There is a risk of the 2 individuals not communicating well or having disagreements early-on which can reduce productivity. 

- Real World Example (VMWare Tanzu):
This format is used on VMWare and is enforced regularly with full-time paired programming accross most if not all engineering teams. By doing this, it result in reducing long-term technical and developmental debt and also decreased the debugging costs down the line. 
   
Q3.) Write 3-4 sentences explaining how that practice would help the Scrum/Kanban workflow you
simulated in Task 1 stay sustainable at speed.
This type of paired programming practice acts as a real-time quality gate that keeps the task 1 Kanban workflow working continously and with very little error, whilst still operating at an efficient speed. By setting a WIP limit of 2, any delay in code reviews would stall the board and cause bottlenecks in the workload. While a pair reviews story 1 (Calendar View) while typing, the features moves to a 'Done' status without waiting for an indepedent code reviewer. This ensures that development teams can achieve a one-dat sprint deadline with very little sacrifice in quality or budget. 
---------------------------------------------------



