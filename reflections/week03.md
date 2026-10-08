Week 3 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------
Task 1 — Change impact tracing (45 min)
Read the change request scenario (a client requests a significant feature change midway through a 6-
month waterfall project)

Q1.) Map out, step by step, what re-work is triggered in a waterfall process (docs, sign-offs, re-testing)
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

Q2.) Now assume the same team was working in 2-week increments — re-trace the impact
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
   
Q3.) Compare the cost/effort of the change under each approach
Waterfall: 
- Process Overhead (High): Changes require a formal impact analysis and meetings to be held to analyse its impact.  
- Documentation (High): Documentation must be frequently updates and 
- Rework:
- Testing: 
- Financial And Timeline Risk: 

Agile: 
- Process Overhead: 
- Documentation:
- Rework:
- Testing: 
- Financial And Timeline Risk: 
   

-----------------------------------------------------------------------------------------------------
Task 2 — Heavyweight, Lightweight, or No Process at All? (45 min)
Read the QuickBuild Solutions team process description in this week's handout

Q1.) Identify three specific weaknesses in how QuickBuild works

Q2.) For each weakness, decide: is this something a disciplined lightweight/agile process would actually catch
and prevent, or is it simply the absence of any process at all? Justify your answer using this week's
heavyweight-vs-lightweight framing

Q3.) Propose one concrete, low-cost improvement for each wea
