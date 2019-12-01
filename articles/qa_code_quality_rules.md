# Introduction to Code Quality Rules
[Link](https://www.baeldung.com/code-quality-metrics)  
## Cyclomatic Complexity (CC)
* Describes structural complexity of code
* CC value can be calculated by measuring the number of independent execution paths of a program.
* CC takes into account the nesting of conditional statements and multi-part boolean expressions.
* Rule of thumb: CC > 11 is considered very complex and difficult to test and maintain
* The higher the CC, the higher the difficulty to implement pertinent tests
* How to reduce CC?
	* implementing Single Responsibility Principle
	* Avoiding: excessive length of method, too many fields in single class, excessive parameters list
	* Using design patterns instead of lengthy switch statements
## Exception Handling Rules
* Do not throw exception in finally block
	* finally should only be used to release resources (e.g. files), any other use is considered code smell
	* similarly returning in the finally block
* Failing to Close Stream on Exception
	* Closing streams is one of the main reasons why we use a finally block, but it's not a trivial task
## Bad practices
* Null Pointer Dereference (resulting in Null Pointer Exception)
	* Some technics used to avaid NPE:
		* avoid keyword null while coding
		* use @NotNull, @Nullable
		* use java.util.Optional
		* implement Null Object Pattern
