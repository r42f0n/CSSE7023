java c
Advanced Software Engineering (CSSE7023)
Assignment 1 — Semester 2, 2024
School of Electrical Engineering and Computer Science
Due August 27th 13:00 AEST
Overview This assignment delivers practical experience developing a Java project based on a supplied spec-ification. The specification is provided in the form. of JavaDocs, which describe the classes and interfaces that your assignment must implement. You will be assessed on your ability to:
• implement a program that complies with the specification,
• and develop code that conforms to the style. conventions of the course.
Task A role-playing game (RPG) typically involves the players building and controlling characters in a fictional world (either physical or virtual, such as table-top or on-line). Such worlds and characters are governed by the game rules and many things are decided by chance (e.g. by rolling dice). Characters have various attributes, including their primary ”stats”, ”hitpoints” (HP), ”experience” (XP), specialties and features. In this assignment, you will be implementing the Character Building process (only!) for demo world, using a command line interface (in Assignment 2, we will expand to a graphical user interface). The command line interface (CLI) is a text-based terminal interface, where the player will build their ”character” (i.e. a collection of attributes) by asking the player to select various options from a series of choices. Note! You do not need to be familiar with RPGs to complete this assignment. This assignment does NOT implement the RPG. This assignment requires you to implement the CharacterBuilder class to offer a series of choices to the user (in accordance with the game rules), accept the user’s input, and record the resulting choices in the form. of a text-based ”character sheet”, such as shown below and on the next page.

Figure 1: A screenshot of the working Individual Assignment 1 command line interface (CLI).

Figure 2: Another screenshot of the working CLI — note the last choice still requires an input.

Figure 3: Invalid stat allocation choices are ignored and the question is asked again.

Figure 4: A screenshot of the working Individual Assignment 1 character sheet.
Notes on the screenshots The screenshots in Figures 1 to 4 are from the working assignment and replace the samples (mock-ups) provided in the original assignment spec. Some changes to note:
The welcome message says ‘(there will be a pdf written and provided)’. This is not true, the output from Individual Assignment 1 is a text file with the suffix “.sheet” – it is not a PDF. This is part of the provided code. You must not change it.
The actual screenshot from the solution differs from the mock-up sample provided in the original spec. In the scroll, the stats are simply centred, not aligned on the colons; and the hitpoints boxes under the scroll are always empty ‘[ ]’, not with some marked like the sample in the original spec (so that players can manually adjust the markings during game-play). Note the asterisks in the features boxes (adjustments) in the bottom part of the character sheet are required!
Common Mistakes Please carefully read Appendix A. It outlines common and critical mistakes which you must avoid to prevent a loss of grades. If at any point you are even slightly unsure, please check as soon as possible with course staff.
Plagiarism All work on this assignment is to be your own individual work. By submitting the assignment you are claiming it is entirely your own work. You may discuss the overall general design of the application with other students. Describing details of how you implement your design with another student is considered to be collusion and will be counted as plagiarism.
You may not copy fragments of code that you find on the Internet to use in your assignment. Code supplied by course staff (from this semester) is acceptable, but must be clearly acknowledged as described in the next paragraph.
You may find ideas of how to solve problems in the assignment through external resources (e.g. StackOver-flow, textbooks, ...). If you use these ideas in designing your solution you must cite them. To cite a resource, provide the full bibliographic reference for the resource in file called refs.md. The refs.md file must be in the root folder of your project. For example:
1 > cat refs.md
2 [1] E. W. Dijkstra, "Go To Statement Considered Harmful," _Communications of the ACM_,
3 vol 11 no. 3, pp 147-148, Mar. 1968. Accessed: Mar. 6, 2024. [Online]. Available:
4 https://www.cs.utexas.edu/users/EWD/transcriptions/EWD02xx/EWD215.html
5 [2] B. Liskov and J. V. Guttag, _Program development in Java: abstraction,
6 specification, and object-oriented design_. Boston: Addison-Wesley, 2001.
7 [3] T. Hawtin, "String concatenation: concat() vs '+' operator," stackoverflow.com,
8 Sep. 6, 2008. Accessed: Mar. 8, 2024. Available:
9 https://stackoverflow.com/questions/47605/string-concatenation-concat-vs-operator
10 >
In the code where you use the idea, cite the reference in a comment. For example:
1 /**
2 * What method1 does.
3 * [1] Used a method to avoid gotos in my logic.
4 * [2] Algorithm based on section 6.4.
5 */
6 public void method1() ...
8 /**
9 * What method2 does.
10 */
11 public void method2() {
12 System.out.println("Some " + "content.") // [3] String concatenation using + operator.
13 }
You must be familiar with the university’s policy on plagiarism.
https://uq.mu/rl553
If you have questions about what is acceptable, please ask course staff.
Generative Artificial Intelligence You are required to implement your solution on your own, without the use of generative artificial intelligence (AI) tools (e.g. ChatGPT or Copilot). This is a learning exercise and you will harm your learning if you use AI tools inappropriately. Remember, you will be required to write code, by hand, in the final exam.
Specification
The specification document is provided in the form. of JavaDocs.
◦ Implement the classes and interfaces exactly as described in the JavaDocs.
◦ Read the JavaDocs carefully and understand the specification before programming.
◦ Do not change the public specification in any way, including changing the names of, or adding additional, public classes, interfaces, methods, or fields.
◦ You are encouraged to add additional private members, classes, or interfaces as you see fit.
You can download the JavaDoc specification from BlackBoard (Assessment → Individual Assignment 1) or access it at the link below.
https://csse7023.uqcloud.net/assessment/assign1/docs/
Getting Started
To get started, download the provided code from BlackBoard (Assessment → Individual Assig代 写CSSE7023 Advanced Software Engineering Assignment 1 — Semester 2, 2024Java
代做程序编程语言nment 1). Extract the archive in a directory and open it with IntelliJ.
Task
Implement each of the classes and interfaces described in the JavaDoc specification.

Figure 5: Updated class diagram of the specification for Individual Assignment 1.
Grading
Three aspects of your solution will considered in grading your submission. These are functionality, automated style. check, and human readable style.
Functionality
Each class has a number of unit tests associated with it. Your grade for functionality is based on the percentage of unit tests you pass. Classes may be weighted differently depending on their complexity.
Automated Testing  Checking
Functionality and style. check grading will be done automatically in a Linux environment. The environment will not be running Windows, and neither IntelliJ nor Eclipse (or any other IDE) will be involved. OpenJDK 21 with the JUnit 4 library will be used to compile and execute your code. To prevent infinite loops, or malicious code, from slowing down Gradescope, any test that takes longer than 10 seconds to execute will be killed and identified as failing.
IDEs like IntelliJ provide code completion hints. When importing Java libraries they may suggest libraries that are not part of the standard library. These will not be available in the test environment and your code will not compile. When uploading your assignment to Gradescope, ensure that Gradescope says that your submission was compiled successfully.
Your code must compile.
If your submission does not compile, you will receive no marks.
Automated Style. Check
Your grade for automated style. checking is based on the number of style. violations identified by the Checkstyle. tool. It will be run in the same environment as the JUnit automated functionality tests. Multiple style. violations of the same type will each count as one additional violation.
Note: There is a plug-in available for IntelliJ that will highlight style. violations in your code. Instructions for installing this plug-in are available in the Java Programming Style. Guide on BlackBoard (Learning Resources → Guides). If you correctly use the plug-in and follow the style. requirements, it should be relatively straightforward to get high grades for this section.
Human Readable Style.
Course staff will grade the readability of the code you submit. This will assess the structure, style, documentation and logic of your code. The high-level evaluation is how easily can another programmer, who is familiar with Java, understand your code. This includes layout of code, use of descriptive identifier names, and concise and informative comments. It also includes the detailed design of your code’s logic and how much code is unnecessarily duplicated. See Appendix B for criteria that will be used to assess the readability of your code.
Submission
Submission is via Gradescope. Submit your code to Gradescope early and often. Gradescope will give you some feedback on your code, but it is not a substitute for testing your code yourself.
What to Submit Your submission must have the following internal structure:
src/                           folders (packages) and .java files for classes described in the JavaDoc.
refs.md                file containing the references for any citations in your code.
Included in the root directory of the provided code are the files bundle.sh and bundle.cmd. For MacOS and Unix users, run $bash bundle.sh file to execute it. For Windows users, double-click the bundle.cmd file to execute it. This will create a submission.zip file for you to upload to Gradescope.
You can create the submission zip file yourself using a zip utility. If you do this, ensure that you do not miss any files or directories. Also ensure that you do not add any extra files. We recommend using the provided bundle scripts.
Ensure that your classes and interfaces correctly declare the package they are within. For example, Character.java should declare package demoworld.model;.
Only submit the src folder and the refs.md file in the root directory of your project.
Do not submit any other files (e.g. no .class files or IDE files).
Provided tests A small number of the unit tests (about 10-20%) used for assessing functionality will be provided in Gradescope. These will be used to test your submission, each time you upload it.
These are meant to provide you with an opportunity to receive feedback on whether the basic functionality of your classes works correctly or not. Passing all the provided unit tests does not guarantee that you will pass all the tests used for functionality grading.
Assessment Policy
Late Submission You must submit your code before the deadline. Code that is submitted after the deadline will receive a late penalty as described in the course profile. The submission time is determined by the time recorded on the Gradescope server. A submission is not recorded as being received until uploading your files completes. Attempting to submit at the last minute may result in a late submission.
You may submit your assignment to Gradescope as many times as you wish before the due date. There will be two submission links on Gradescope, one for “on-time” submissions and one for “late” submissions. If you have an extension for the assignment, you will submit your assignment via the “late” submissions link. Your last submission made to the “on-time” submission link, before the due date, will be the one that is graded, unless you make a submission to the “late” submission link. If a misconduct case is raised about your submission, a history of regular submissions to Gradescope, which demonstrate progress on your solution, could support your argument that the work was your own.
You are strongly encouraged to submit your assignment on time, or by the revised deadline if you have an extension. Experience has demonstrated that most students who submit their assignments late lose more grades due to the late penalties than they gain by making improvements to their work.
Extensions If an unavoidable disruption occurs (e.g. illness, family crisis, etc.) you should consider applying for an extension. Please refer to the following page for further information.
https://uq.mu/rl551
All requests for extensions must be made via my.UQ, before the submission deadline. Do not email the course coordinator or other course staff to request an extension.
Re-Grading If an administrative error has been made in the grading of your assignment, please contact the course coordinator ([email   protected]) to request this be fixed. For all other cases, please refer to the following page for further information.
https://uq.mu/rl552





         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
