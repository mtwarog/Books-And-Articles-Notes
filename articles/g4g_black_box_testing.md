# Black box testing 
(part of Software Engineering on Geeks4Geeks, Software Testing and Debugging)  
[Link to article](https://www.geeksforgeeks.org/software-engineering-testing-guidelines/)  
**Definition**: Black box testing is a type of software testing in which the functionality of the software is not known.  
* The testing is done without the internal knowledge of the products.
## Ways of doing Black Box testing
* Syntax Driven Testing
	* This type of testing is applied to systems that can be syntactically represented by some language. For example- compilers,language that can be represented by context free grammar. In this, the test cases are generated so that each grammar rule is used at least once.
* Equivalence partitioning
	* It is often seen that many type of inputs work similarly so instead of giving all of them separately we can group them together and test only one input of each group. The idea is to partition the input domain of the system into a number of equivalence classes such that each member of class works in a similar way
* Boundary value analysis
	* Boundaries are very good places for errors to occur. Hence if test cases are designed for boundary values of input domain then the efficiency of testing improves and probability of finding errors also increase.
* Cause effect Graphing
	* This technique establishes relationship between logical input called causes with corresponding actions called effect. The causes and effects are represented using Boolean graphs
* Requirement based testing
	* It includes validating the requirements given in SRS of software system.
* Compatibility testing
	* The test case result not only depend on product but also infrastructure for delivering functionality. When the infrastructure parameters are changed it is still expected to work properly