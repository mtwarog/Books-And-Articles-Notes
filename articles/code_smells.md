# Code Smells	
[Wiki](https://en.wikipedia.org/wiki/Code_smell)  
**Definition**: "a code smell is any characteristic in the source code of a program that possibly indicates a deeper problem"  
* What is a code smell is subjective and varies by language, developer and development methodology.  
* Origin: Term was popularized by Kent Beck on WardsWiki in the late 1990s. Usage of the term increased after the book "Refactoring: Improving the Design of Existing Code" by Martin Fowler.  
* "Smells are certain structures in the code that indicate violation of fundamental design principles and negatively impact design quality"  
* Code smells are usually not bugs, they are not technically incorrect.  
* They indicate weaknesses in design that may slow down development or increase the risk of bugs or failures in the future.  
* There are tools for automate smells detection like FindBugs for Java  
## Common code smells
* Application-level
	* Duplicated code
	* Contrived complexity: forced usage of overcomplicated design patterns where simpler design would suffice.
	* Shotgun surgery: a single change needs to be applied to multiple classes at the same time.
* Class-level
	* Large class: a class that has grown too large. See God object.
	* Feature envy: a class that uses methods of another class excessively.
	* Inappropriate intimacy: a class that has dependencies on implementation details of another class.
	* Refused bequest: a class that overrides a method of a base class in such a way that the contract of the base class is not honored by the derived class. See Liskov substitution principle.
	* Lazy class / freeloader: a class that does too little.
	* Excessive use of literals: these should be coded as named constants, to improve readability and to avoid programming errors. Additionally, literals can and should be externalized into resource files/scripts, or other data stores such as databases where possible, to facilitate localization of software if it is intended to be deployed in different regions.
	* Cyclomatic complexity: too many branches or loops; this may indicate a function needs to be broken up into smaller functions, or that it has potential for simplification.
	* Downcasting: a type cast which breaks the abstraction model; the abstraction may have to be refactored or eliminated.
	* Orphan variable or constant class: a class that typically has a collection of constants which belong elsewhere where those constants should be owned by one of the other member classes.
	* Data clump: Occurs when a group of variables are passed around together in various parts of the program. In general, this suggests that it would be more appropriate to formally group the different variables together into a single object, and pass around only this object instead.
* Method-level
	* Too many parameters: a long list of parameters is hard to read, and makes calling and testing the function complicated. It may indicate that the purpose of the function is ill-conceived and that the code should be refactored so responsibility is assigned in a more clean-cut way.
	* Long method: a method, function, or procedure that has grown too large.
	* Excessively long identifiers: in particular, the use of naming conventions to provide disambiguation that should be implicit in the software architecture.
	* Excessively short identifiers: the name of a variable should reflect its function unless the function is obvious.
	* Excessive return of data: a function or method that returns more than what each of its callers needs.
	* Excessively long line of code (or God Line): A line of code which is too long, making the code difficult to read, understand, debug, refactor, or even identify possibilities of software reuse.
## Code smells classification
* Bloaters - Bloaters are code, methods and classes that have increased to such gargantuan proportions that they are hard to work with. 
* Object-orientation abusers - All these smells are incomplete or incorrect application of object-oriented programming principles.
* Change Preventers - if you need to change something in one place in your code, you have to make many changes in other places too.
* Disensables - A dispensable is something pointless and unneeded whose absence would make the code cleaner, more efficient and easier to understand.
* Couplers - All the smells in this group contribute to excessive coupling between classes or show what happens if coupling is replaced by excessive delegation.