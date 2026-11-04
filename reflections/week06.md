Week 6 — Research Lab

Tasks:
-----------------------------------------------------------------------------------------------------

---------------------------------------------------
Task 1 — Manual code walkthrough (30 min)
Q1.) In pairs, read the code sample line by line.
   
Q2.) Count the independent decision points (if / else if, loops) by hand and compute its cyclomatic
complexity as decision points + 1. Say whether it crosses McCabe's threshold of 10.

There are 10 different decision points, including: 
1. if (dest.equals("LOCAL")) 
2. if (wt < 1) (inside LOCAL) 
3. else if (wt < 5) (inside LOCAL) 
4. else if (dest.equals("NATIONAL"))
5. if (wt < 1) (inside NATIONAL) 
6. else if (wt < 5) (inside NATIONAL) 
7. if (wt < 1) (inside international else) 
8. else if (wt < 5) (inside international else) 
9. if (p)
10. if (q > 10)

The cyclomatic complexity is 10 + 1 = 11. 
Yes, it crosses McCabe's threshold of 10. Due to it having a complexity of 11, it means the code has too many execution paths, 
making it complex and more prone to errors and issues during testing without refactoring.

Q3.) Identify duplicated logic, unclear naming or other maintainability concerns you can spot just by reading.

- Dupelicate Logic:
In this code, the 3 main branches of "LOCAL", "NATIONAL" and "ELSE" repeat the same nested conditional logic of:
  - if (wt < 1)
  - else if (wt < 5)
  - else

 These duplications increase the the amount of methods in the code, meaning that if future modiciation were to occur, 
 weight boundaries would have to be manually applied and tested in each of the 3 seperate code blocks. 

- Unclear Naming:
There are many unclear parameters and naming in this code that are uninformative and do not explain their purpose, such as:
  - double wt = Package weight.
  - String dest = Region destination.
  - boolean p =  Promotional discount flag. 
  - int q =  Item quantity count.
  - double c = Calculated shipping cost.

Without properly nameing and describe the variables, a developer can not understand the purpose of these metrics without further understanding 
the rest of the code, making it difficult for involvement of 3rd party coders and teams. 

- Maintainability Concerns:
In this code, there are no validation or error handling checks for incoming data before calculating the cost, for example:
- While passing a negative value for the weight ("wt = -5"), this would bypass the "<1" check and directly fall into the first branch, resulting
in an invalid charge without throwing any sort of error.

- If "dest" is passed as a null, then the call "dest.equals("LOCAL") would trigger a runtime error of "NullPointerException" and crash the
the system. 
   
Q4.) Say which of these concerns are internal attributes you could measure, and which need human
judgement.

- Measureable:
  - Duplicated Code: Software tools, such as SonarQube, can flag duplicate code automatically and calculate the
  percentage of repeated lines of code for the user to see and remove.
    
  - Unclear Naming: A linter tool can be used to measure the character length of variables or check if their names
  go against any standard naming conventions and flag them for clarity.
    
  - Error Handling: Static analysis can be used by the user to scan for any lack of of input guards, null-pointer, or unclear
  or non-existant erorr handling and exceptions to check blocks.


- Require Human Input:
  - Name Clarity: While the system may be able to identify and differentiate what the value "p" means,
  humans and typical users do not know this, making it confusing and unclear because it may stands for many other
  variables or names.
    
  - Design: When deciding how to removing duplicated code, whether to use use lookup databases, an enum class,
  or a separate strategy pattern object—requires, all requires the system architect's decision.
    
  - Error Handling: The user must decide how the system should respond to invalid inputs, more speciailly, 
  whether a inputed negative weight should crash the system with an exception, throw anerror message, or change the
  input to zero.
---------------------------------------------------

---------------------------------------------------
Task 2 — Defect density (15 min)
Q1.) System A has 45 known defects in 30 KLOC. System B has 15 known defects in 6 KLOC. Compute the
defect density of each (known defects / product size) and say which looks better.

- System A:
  - Known Defects: 45
  - Size: 30 KLOC
  - Calculation: 45/30 = 1.5 defects/KLOC

- System B:
  - Known Defects: 15
  - Size6 KLOC
  - Calculation: 15/6 = 2.5 defects/KLOC
 
System A has a significanntly lower defect density of 1.5 defects per 1 thousand lines of code, compared to system B, which has 
a higher density of 2.5 defects per KLOC. This demonstrates that system A's codebase is more streamlined and efficient, or has been through 
quality assurance in terms of checking its size. 

Q2.) Using the lecture's cautions about defect density, give three reasons why the comparison may be unfair.

- Testing Effort Variance: The defect density relies solet on the known defects of a system. System B, with 2.5 defects/KLOC, may have
been through more testing than compared to System A, meaning that it discovered more hidden bugs and errors rather than having a lower
quality codebase score. 
  
- Lack Of Severity Context: This metric treats defects as identical numbers. System A has 45 defects, which may conssity of critical errors
such as security vulnerabilities or errors that may completey crash the system, while system B's defects may only be minor errors, such as
UI problems that do not effect the functionality of the system. 
  
- KLOC Flaws: Lines of code do not scale linearly with system complexity. If the system were to be written in a different programming language
or if one the codebases includes a larger number of generated boilerplate code, then the size diviors becomes sweked and creates a inaccurate
density value. 
   
Q3.) Compare each figure with the reported evidence in the lecture (the USA/Europe average, and the level
considered good).
Based on the lecture material, it states that the USA/Europe industry has an average of 5-10 defects per KLOC, while the delivered density 
level is below 2 defects per KLOC, which is considered good. 

- System A: This system has 1.5 defects/KLOC, which is much lower than the average and is significantly cleaner than most systems in terms of the USA/Europe
value of 5-10. Additionally, it exceeds the target of <2/KLOCK and is within the "good" classification. 
  
- System B: This system has 2.5 defects/KLOC, which is below the average again, and still is better than most industry standards. However,
It misses the target and is slightly higher than the benchmark required for the "good" classification. 
---------------------------------------------------

---------------------------------------------------
Task 3 — Portfolio entry (10 min)
Q1.) Commit your annotated code sample and defect density calculations to GitHub under week06/.
---------------------------------------------------

-----------------------------------------------------------------------------------------------------
