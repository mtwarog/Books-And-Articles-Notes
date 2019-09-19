# StackOverFlowError in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-stack-overflow-error)  
**Purpose**: Informs about failure caused by exceeding memory of Stack, which keeps track of local variables and function calls
## Stack Frames and How StackOverflowError Occurs
* When a method is called, a new stack frame gets created on the call stack
* "This stack frame holds parameters of the invoked method, its local variables and the return address of the method i.e. the point from which the method execution should continue after the invoked method has returned."
* if JVM encounters a situation where there is no space for a new stack frame to be created, it will throw a StackOverflowError.
* The most common cause for the JVM to encounter this situation is unterminated/infinite recursion
* Other causes:
	* having a vast number of local variables inside a method
	* calling methods until the stack is exhausted
	* application is designed to have cyclic relationships between classes. In this situation, the constructors of each other are getting called repetitively which causes this error to be thrown. This can also be considered as a form of recursion.
	* if a class is being instantiated within the same class as an instance variable of that class. This will cause the constructor of the same class to be called again and again (recursively) which eventually results in a StackOverflowError.
## Dealing with StackOverFlow
* The best thing to do when a StackOverflowError is encountered is to inspect the stack trace cautiously to identify the repeating pattern of line numbers.
* The -Xss flag can be used to increase the size of the stack, either from the project’s configuration or the command line. 
## Questions:
* What is the purpose of Stack Trace in general? What are alternatives?
	* keeping track of where to return after function call
	* creating new scope for each function call