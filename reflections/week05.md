Week 5 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------

---------------------------------------------------
Task 1 — Quality scoring (45 min)
Q1.) In pairs, score the chosen application on each of the 8 ISO/IEC 25010 characteristics (1-5 scale).

I have chosen Github for this: 
- Functional Suitability - Score: 5/5:
It provides core Git features, pull requests and issues work seamlessly without any additional configuration. 

- Performance Efficiency - Score: 3/5:
While on average it performs well and without issue, however, at certain times depending on the respository or page I am accessing
it can suffer from latency and lag time. Additionally, actions such as pull or push requests can be slow when first initiated.

- Compatibility - Score: 5/5:
It incorporate seamless inegration with local IDEs, APIs and operating systems without formatting issues. 

- Usability - Score: 2/5:
Clean, but detailed Ui that is easy to use. However, it can become convuluted when searching for specific features. 
  
- Reliability - Score: 5/5:
Github has a high overall uptime and is always avaiable and functioming properly when I need it. 

- Security - Score: 5/5:
It has mandatory MFA, signed commits and automated secret scanning to prevent unhashed credentialsl
in push logs. 

- Maintainability - Score: 4/5:
The UI is seperated in a clean and usable format, thouh managing massives rails core require strict dependency rules. 

- Portability - Score: 5/5:
Github is highly portable on most web browsers, meanign that I can access it no matter what device I using. 


---------------------------------------------------
Q2.) For each score, note the specific evidence used (a bug found, a slow response, unclear navigation, etc.).

- Functional Suitability:
Seamless core features operating out of the box; Git workflows, pull requests, and issue tracking require zero additional configuration or workarounds.

- Performance Efficiency:
Slow response times and lag when accessing specific pages. ALso, some delay when initiating a git pull or push command.

- Compatibility:
No format mismatches or system conflicts when exchanging data across operating systems, external APIs, or developer IDEs.

- Usability:
Certain convoluted layouts that make finding specific features difficult, despite having it having a clean visual UI.

- Reliability:
High uptime with no unexpected crashes or failures that I have encountered.

- Security:
Automated security mechanism that block unhashed credentials in push logs, alongside multi-factor authentication (MFA).

- Maintainability:
Clean UI separation of front-end components, but has strict dependency rules in the core framework.

- Portability:
Cross-platform execution across web browsers, allowing for consistent usage on any device.
  
---------------------------------------------------
Q3.) Identify the two weakest characteristics.
Two of its weakest characteristics would be performance effiency (3/5) due to latency/lag when attempting to access heavy repositories and slow initial pull.push requests, as well as and usability (2/5) due to convoluted navigation when searching for specific features. 

---------------------------------------------------
Q4.) For one characteristic, note which 'view' of quality (user, manufacturing, product, etc.) your scoring
approach most reflects.
The scoaring for usability most closely reflects the user view of quality. The user view refers to quality based on the a system's overall accessibility and how well the system meets the cosumer's needs and perferences. 

My score for usability of 3/5 direct reflects my own personal experience of using Github and how well it functioned from my perspective. I stated that searching for specific features was "convoluted" , refering to my issues on my end in terms of navigating the site rather than an issue with Github's internal code or a delpylment failure. 

-----------------------------------------------------------------------------------------------------


-----------------------------------------------------------------------------------------------------
Task 2 — Trade-off analysis (25 min)

---------------------------------------------------
Q1.) Choose one improvement that would raise one of the weak characteristics
To address my issues with Github's usability, I have chosen to use a unified command palette to fix any issues with search logic. What this does is insteaad of users clicking aimlessly through nested settings and respositories to find a specific element that they wish to view, they can type the name of any aciton, setting or repository location dierectly into the gloval search field at the top of the site. This solves the issues of the UI and interfaces becoming confusing by allowing the user to directly and quickly what they are looking for on any page of the platform. 

---------------------------------------------------
Q2.) Analyse what it would cost in terms of another characteristic (e.g., adding validation improves reliability
but may hurt performance)
Implementing a unified command pallete would fix my usability issues, but may cost performance efficiency. A command palletewould require fuzzy search matching that indexes repositories, settings and user profiles in real time as the user types. From this, fetching and querying these data models on every keystroke would cause hugh CPU usage and would increase the browser's memory consumtpion. If not regulated and optomised, real time indexing would create input lag and latency, worsening GitHub's performace. 

---------------------------------------------------
Q3.) Write a short justified recommendation: is the trade-off worth making?
Yes, I beliebe that is a justifiable trade-off to implement this feature. The benefits in user experience far outwieght the perfomance costs that may arise from its implementation. Navigation issues impact most users on almost every platform available. Resolving convuluted nagviation not only benefits GitHub's overall public perception but also improves the average user's experinece, encouraging them to use the application more often 

Additionally, unlike architectural system bloat, search latency is a problem that has many technical solutions and performance costs can be easily controlled, or at least minimised, through debouncing inputs to delay data quieries as user types, local caching most frequenctly access elements/features or asychronous fetching to ensure bacjground indexing does not lock up the main UI. 

By introducing strict performance methods, GitHub can easily improve its user navigation wihtout causing significant loss in its performance efficiency. 


-----------------------------------------------------------------------------------------------------


-----------------------------------------------------------------------------------------------------
Task 3 — QA or QC? (20 min)

---------------------------------------------------
Q1.) Using Handout B, sort the 12 activity cards into Quality Assurance (QA) and Quality Control (QC), with a
one-line reason for each

- Quality Assurance (QA):
  - 1.) Writing a coding standard for the team.
    Reasoning: Ensures a quality standard for code to be developed to a high degree. 
    
  - 3.) Auditing whether teams actually follow the review procedure.
    Reasoning: Allows for the verifcation of and validation that the team is following the correct and preestablish workflow. 
    
  - 5.) Defining the steps of the change-control procedure.
    Reasoning: Determines a preventative framework that the team must follow in order to make changes to the project. 
    
  - 7.) Training new starters in the team's testing approach.
    Reasoning: Guarantees new members are aware of the current workflow and approach to the system. 
    
  - 9.) Deciding which quality characteristics matter most in the quality plan.
    Reasoning: Sets the criteria for the projects lifecycle and ensures that quality characteristics are met above all else. 
    
  - 11.) Collecting defect counts and reviewing them to change how the team works.
    Reasoning: Uses historical data to modify the ongoing development process in order improve and keep it on track. 


- Quality Control (QC):
  - 2.) Running the unit test suite before a change is merged.
    Reasoning: Evaluates a project feature and to test that it functions correctly before merging. 
    
  - 4.) Peer review of one pull request.
    Reasoning: Verifies the code to determine any bugs or issues before deployment. 
    
  - 6.) Running a static-analysis tool over the code base.
    Reasoning: Helps to scan the system for existing issues, such as security problems or syntax issues. 
    
  - 8.) User acceptance testing of the finished feature.
    Reasoning: Measures the product against establish user requirements to understand if their needs are met and to detect functionality gaps. 
  
  - 10.) Inspecting a design document against the team's template.
    Reasoning: Cehcks specific deliverables to find whther it meets or fails its constraints. 
    
  - 12.) Penetration testing the login page.
    Reasoning: A security test to ensure that the login correctly and securely stores user credentials and to expose any possible vulnerabilities. 

---------------------------------------------------
Q2.) Pick the cards you found hardest to place, and state the definition of QA and QC you used to decide

Definitions Used: 
- QA: A systematic and proactive approach framework designed to prevent defects in a product and to ensure that it meets specified standards and customer requirements. 
  
- QC: A process of inspecting, testing and measuring products against a prestablish standard to detect defects or issues and taking corrective action.

I found it hard to place Card 4 and card 10, because: 

- Card 4 Peer review of one pull request (QC) :
Pull requests happen during development and teams view peer code reviews as part of the QA framework already. Based on the definition of QC, this involes inspecting and testing specific code against pre-establihs standards and because the goal is to detect issues within that pull request before it is merged, it functions as a QC activity. 

- Card 10 Inspecting a design document against the team's template(QC):
Templates are created early in a products lifecycle to create a standrad process and a design document is created before the any work on the prodct even begins, meanign it is more in line with QA. However, based on the definition of QC, the template is a pre-establish standar , but the act of inspecting and measuring a document against the template is an inepection step. Meaning you are chking a specific deliverable to detect problems, making it a QC activity. 

---------------------------------------------------
Q3.) For the weakest characteristic from Task 1, name one QA activity that would help prevent the weakness
and one QC activity that would detect it

- Usability:
- QA Activity: Creating a UI navigation stardard.
Before any code is developed or written, the team must first establish a framework to base their work on. This standard would then ensure that any new feature that is implemented must be easily accessible to all users from the main dashboard. By enforcing this design process in the begininng, it prevents any convoluted nagivation design from being built into the product.
  
- QC Activity: User Acceptance Testing.
When new features are built and implemented, the team should conduct user testing session. These sessions would allow users to test the product to ensure that it meets all their requirements and to ensure the product operates as intended. The team may also measure the users test performance against the baseline to understand where the product falls short in terms of functionality and performance. If users have issues with the product, such as navigation, then this problem is logged and and analysed for future improvements. 
  
-----------------------------------------------------------------------------------------------------


-----------------------------------------------------------------------------------------------------
Task 4 — Standards for a small team (20 min)

---------------------------------------------------
Q1._ Imagine a four-person student team building the next release of your chosen application. Write two
product standards and two process standards for the team (Handout C has examples to adapt, not copy)

- Product Standards:
* 1.) The first standard would be a keystroke latency cap and payload limit. The current payload of indexing inside the client's browser must have a certain threshold that it can't exceed, such as 2MB of memory, and the user interface must rendder results within a certain timelimit. This standard would allow the team to enhance their product's performance and by enforcing limits to certain areas, would allow them to decrease data volume and rendering times. 

* 2. ) The second standard would outline a fixed UI design layout that the team must follow. This would mandate and ensure that every feature or function that is implemented into the product would follow a strict guidline how it positioned and fit among the rest of the system. More specifically, the team could enforce a minimum text to background ratio along with a strict visual hierarchy to highlight the key points of the system. This would protect usability and make sure that the system is easily readable and removes any complex design elements. 
  
- Process Standards:
* 1.) The first process would be through ansynchronous database query architecture. Before any of the base code is written, the team must create diagrams and prototypes to prove that their design and all data fetching functions work asychronously with eachother. This would enhance performance effieicny and improve reliability by enforcing reviews on heavy quieries or large repositories from blocking the main feed and prevent drops in operation.

* 2.) The second process is through a shared component validation. When a team member introduces externa; packages or any third part sources to assist with indexing, they first must run a dependency analysis during their build to verify its scalability and adaptability with another member. This would protect the maintainability of the system as it ensures that any new features remain isolated from the rest of the code, preventing it from causing any possible errors or risks to the rest of the system and to keep the main code clean and streamlined. 

---------------------------------------------------
Q2.) For each standard, say which ISO/IEC 25010 characteristic it protects.

- Product Standards:
* 1.) Keystroke latency cap and payload limit: This would protect performance effiency by descreasing data volumeand rendering times to prevent lag under large payloads. 
  
* 2.) Fixed UI Design Layout: This protects usability to ensure the system is easily reabale and removes complex design elements. 

- Process Standards:
* 1.) Asynchronous Database Query Architecture: This protects performance efficient and reliability by enforcing reviews to prevent heavy respotiory queries from bloacking the main feed and preventing system freezes and lag. 
  
* 2.) Shared Component Validation: This protects maintainability by keeping kew features isolated to prevent errors and integration risks. 


---------------------------------------------------
Q3.) For each standard, say how a QA activity would check that it is being followed, and how a QC activity
would check that the product meets it.

- Product Standards:
Keystroke latency cap and payload limit:
- QA: A spring clanning check can be used to verify that the performance budget tracking is integrated into the shared repository.
- QC: The team can run an automated pipline load test to simulated large card repositoryies to verify that the memory stays below the 2MB threshold and render laytency says under 100ms. 
  
Fixed UI Design Layout:
- QA: The team can review the design guidlines before coding to confirm that the layout is explicity built using components from the design system library and based off of requirements and other forms of feedback.
- QC: A accessibility scan can be used to verift the text to background contrat ratiom eets the 4:5:1 requirements.

- Process Standards:
Asynchronous Database Query Architecture:
- QA: A mandatory peer sign off before any sprints tasks take place and more to "In progress" to ensure the system architecure diarams are approve.
- QC: Hold a peer code review meeting on final pull requests and inspect code to ensure asynchronous syntax and backend functions are implemented. 

Shared Component Validation:
- QA:Check the management board to ensure that dependecy analytsis reports are created and attached to their respective ticket before merging code. 
- QC: Run a dependency audit on the compiled system to confirm the new module remains isolated and free from the rest of the code.
-----------------------------------------------------------------------------------------------------


-----------------------------------------------------------------------------------------------------
Task 5 — Portfolio entry (10 min)

---------------------------------------------------
Q1.) Commit your scoring sheet, trade-off recommendation, card sort and standards sheet to GitHub under
week05/
-----------------------------------------------------------------------------------------------------
