Week 3 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------
Task 1 — Change impact tracing (45 min)
Read the change request scenario (a client requests a significant feature change midway through a 6-
month waterfall project)

---------------------------------------------------
Q1.) Map out, step by step, what re-work is triggered in a waterfall process (docs, sign-offs, re-testing).
- Process And Sign-Offs:
1.) This change must first be logged into a Change Request Register and any features that are currently being worked on must be paused until further notice.
2.) System architects and tech leads now must evaluate on how to exactly split orders and how this will change the original project scope as well as it's timeline and overal cost.
3.) The new changes and analysis aresent to stakeholders to keep them updated.
4.) Due to these new changes, they must be first signed-off by the university head before any new work begins. 

- Documentation:
1.) User requirements must be updated to include the new feature.
2.) Database schemas must now be redesigned to add and change existing data tables to fit this new request.
3.) The existing UI, such as checkout or ordering, must be changed/integrated in order to house multiple restauraunt orders.
4.) System tests must take place to ensure that multiple restauraunt ordering opperated wihtout issue and to ensure that there is no problem with restauraunt routing, payments, etc.

- UI Rework:
1.) System developers must now reqrite existing UI, such as checkout screens, payment gatewats, order tracking screens, etc, to handle the newly added arrays for different items across multiple restauraunts instead of single restauraunt orders.
2.) The database must be altered in order to store data relating to this feature without change to the original database.
3.) Due to this feature being requested later in the cycle, testing will begin much later. From this. testing teams must test the entire system thoroughly, especially the new feature, within week 5 to ensure that every component is operational and functioning correctly before the final system release. 

---------------------------------------------------
Q2.) Now assume the same team was working in 2-week increments — re-trace the impact.
- Request Handling:
This newly request feature will be placed in the product backlog by the product owner for the team to asses when the current workload is completed.

- Documentation:
The requirements are defined iteratively through user defined criteria, and would not require more extensive documentation. 
  
- Scope:
In terms of the timeline, more important requirements or work to be done in the backlog will be pushed forward in order of priority to ensure it does not delay delivery. 
  
- Rework:
Due to the 2-week increments, the system architecure and code will be made in segments which allows for database scehemas and UI to be changed intermittently and without much issue as it continues to evolve. 
  
- Testing:
Testing is done in a sprint in order to ensure that any new logic, such as new features, work correctly to prevent bottlenecking at the end of the project cycle. 

---------------------------------------------------
Q3.) Compare the cost/effort of the change under each approach.
Waterfall: 
- Process Overhead (High): Changes require a formal impact analysis and meetings to be held to analyse its impact.  
- Documentation (High): Documentation must be frequently updated and design documents and test plants must be re-elvaluated before coding is done. 
- Rework (High):System structure already in place (Backend, databases, UI screens, etc) must be reworked and rewritten to incorporate new code. 
- Testing (High): Entire system testing must be completed again to ensure that the system functions correctly and must be done in a fast manner to prevent bottlenecking and system delay.  
- Financial And Timeline Risk (Severe): High likelyhood of schedule overrun and additional labour requires extended budget.  

Agile: 
- Process Overhead (Low): Handled during standard sprint planning with no extra meetings required.  
- Documentation (Low): Documentation is created using user criteria on the go. 
- Rework (Minimal): Code is built in easily modifiable segments that allow for amendments. 
- Testing (Continuous): New logic and code is tested quickly during the sprint and discovers errors and bugs early.  
- Financial And Timeline Risk (Moderate): Project cost and deadline stay within reach, but must be monitored frequently to ensure this.  
   

-----------------------------------------------------------------------------------------------------
Task 2 — Heavyweight, Lightweight, or No Process at All? (45 min)
Read the QuickBuild Solutions team process description in this week's handout

---------------------------------------------------
Q1.) Identify three specific weaknesses in how QuickBuild works.

1.) Memory-Based Requirements: 
Verbal client briefs are relayed through memory with no documentation created to record these requirements. 

- Process Analysis:
  Lacks scope documentation which gile user stories would typically fix. 
  
- Concrete, Low-Cost Improvement:
  Write short user stories based on requirements and get written clieent sign-offs before begining to code. 

2.) Unreviewed Code: 
Code is pushed to the main branch without peer review. 

- Process Analysis:
  Agile prevents this by enforcing peer code review to ensure system reliability. 
  
- Concrete, Low-Cost Improvement:
  Restrict the main branch and require peer approval before merging code. 

3.) Inproper Testing: 
Testing only conssits of the author trying features once before continuing. 

- Process Analysis:
  Agile bypasses validation and acceptance criteria standard. 
  
- Concrete, Low-Cost Improvement:
  Require different developers and coders to test features again user stories before deploying them. 

---------------------------------------------------
Q2.) For each weakness, decide: is this something a disciplined lightweight/agile process would actually catch
and prevent, or is it simply the absence of any process at all? Justify your answer using this week's
heavyweight-vs-lightweight framing.

- Memory-Based Requirements:
Classification: Absence of process.
Justification: Agile processes require an strictly managed and feasible mechanism to base the scope on. By relying only on the team lead’s memory is not a viable solution and lacks basic requirement management and is not lightweight in any means. Heavyweight processes on the other hand use rigid Software Requirements Specifications (SRS), while lightweight processes use dynamic user stories that both require documented agreements.

- Unreviewed Code:
Classification: Prevented by a disciplined lightweight process.
Justification: Agile methods remove unnecessary governance that may hinder a process, but they rely heavily on the correct engineering discipline and peer accountability to produce a functioning and reliable system. Typical practices such as code reviews with approvals from peers help safeguards systems. A disciplined lightweight process prevents unreviewed code by ensuring automated branch protection rules rather than relying on change-control boards.

- Inadequate Developer Testing:
Classification: Absence of any process.
Justification: Testing features exactly once is the absence quality assurance. Heavyweight processes handle situations like thse through documented QA phases and validation protocols.Lightweight processes handle this through shifting testing using automated test-driven development (TDD) which leaves quality up to the developer.

---------------------------------------------------
Q3.) Propose one concrete, low-cost improvement for each weakness, and prioritise your three
recommendations using MoSCoW (Must/Should/Could).

- Memory-based Requirements:
  - Have clients sign off on requirements and changes through having a dedicated repository or tracker for the client. This would prevent trying to base requirements off one person'a memory and would also create another form of documentation which helps developers understand the requirements better.
This is a must because it would prevent misunderstandings with clients and clear up any miscommmunications by creating a direct line of communication between developers and the client. 

- Unreviewed Code:
  - By connecting a repository to an existing communicatins app, such as Microsoft Teams, when a devlopers wants to merge and go live with their code they can upload their code to this application and have their peers review and approve it before finally merging.
This is a should because it ensures code is create to a high degree of quality and helps integrate code into their existing workflow.

- Inproper Testing:
  - Instead of the author singlehandedly testing features once and moving on, they could spend more time testing each feature and ensuring that it is testing is done through a checklist in everytype of enviroment to simulate how a user would use the system to determine any possible bugs that are they are may arise. This would also benefit from create a short video demonstrating each feature for both future review and more documentation if any issues are discovered later.
This is a could because it forces to developer to run these features successfully on video and acts as a visual test so that other developers and users are not surprised by errors or mishandlings as it would be detailed in the video.





