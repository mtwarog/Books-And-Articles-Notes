# White box testing 
(part of Software Engineering on Geeks4Geeks, Software Testing and Debugging)  
[Link to article](https://www.geeksforgeeks.org/software-engineering-white-box-testing/)  
**Definition**: White box testing techniques analyze the internal structures the used data structures, internal design, code structure and the working of the software rather than just the functionality as in black box testing. It is also called glass box testing or clear box testing or structural testing.  
## Working Process of White Box testing
* Input - Requirements, Functional specifications, design documents, source code.
* Processing - Performing risk analysis for guiding through the entire process.
* Proper test planning - Designing test cases so as to cover entire code. Execute rinse-repeat until error-free software is reached. Also, the results are communicated.
* Output - Preparing final report of the entire testing process.
## Testing techniques
* Statement coverage
* Branch coverage
* Condition Coverage
* Multiple Condition Coverage
* Basis Path Testing
	* In this technique, control flow graphs are made from code or flowchart and then Cyclomatic complexity is calculated which defines the number of independent paths so that the minimal number of test cases can be designed for each independent path
* Loop Testing
	* Loops are widely used and these are fundamental to many algorithms hence, their testing is very important. Errors often occur at the beginnings and ends of loops.
## Advatages
* White box testing is very thorough as the entire code and structures are tested.
* Results in code optimization and removing of error
* Easy to automate
## Disadvantages
* It is very expensive
* Redesign of code and rewriting code needs test cases to be written again
* Missing functionalities cannot be detected as the code that exists is tested.
* Complex and at times not realistic