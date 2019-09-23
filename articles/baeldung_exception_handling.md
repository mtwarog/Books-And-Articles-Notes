# Exception Handling in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-exceptions)  
**Purpose**: Code can experience errors (e.g. using external resources (I/O, network etc.)). Exception handling mechanism can handle such cases and move program back to correct state.  
## First Principles
* What is it?
	* Mechanism for handling expected error that might occur during execution
* Why?
	* To increase resillience of code, but forseeing what to do on filesystem corruption, running out of memory, networ failures etc.
* Without handling this exception, an otherwise healthy program may stop running altogether!
## Exception Hierarchy
* All exceptions are extending Throwable
* Throwable 	-> Exception (checked)	-> RuntimeException (unchecked) -> Error (unchecked)
* (there are 3 main categories of exceptions)
	* Checked exceptions
		* Checked exceptions are exceptions that the Java compiler requires us to handle. We have to either declaratively throw the exception up the call stack, or we have to handle it ourselves
	* Unchecked exceptions / Runtime exceptions
		* Runtime and unchecked exceptions refer to the same thing. We can often use them interchangeably. 
		* Unchecked exceptions are exceptions that the Java compiler does not require us to handle.
		* Simply put, if we create an exception that extends RuntimeException, it will be unchecked; otherwise, it will be checked.
		* More on concept of unchecked exceptions (quite controversial topic)
			* https://docs.oracle.com/javase/tutorial/essential/exceptions/runtime.html
		* e.g. NullPointerException, IllegalArgumentException, and SecurityException.
	* Errors
		* Errors represent serious and usually irrecoverable conditions like a library incompatibility, infinite recursion, or memory leaks.
		* Even though they don’t extend RuntimeException, they are also unchecked.
		* e.g. StackOverflowError, OutOfMemoryError
## Handling Exceptions
* we must handle the checked exceptions, and we may handle the unchecked ones. Ways to do that:
* throws 
	* exception can be rethrown e.g. by adding throws in signature of the method
	* it means that user of that method will need to handle or rethrow this exception
* try*catch
	* If we want to try and handle the exception ourselves, we can use a try*catch block
	* catch block can also rethrow the exception
* finally
	* Now, there are times when we have code that needs to execute regardless of whether an exception occurs, and this is where the finally keyword comes in.
	* for e.g. cleanups
* try*with*resources
	* try can automatically close resource implementing AutoCloseable if exception was thrown
* multiple catch blocks
	* Sometimes, the code can throw more than one exception, and we can have more than one catch block handle each individually
	* Java lets us handle subclass exceptions separately, remember to place them higher in the list of catches.
* union catch blocks
	* When we know that the way we handle errors is going to be the same, though, Java 7 introduced the ability to catch multiple exceptions in the same block
	* e.g. ... catch (IOException | NumberFormatException e) ...
## Throwing Exceptions
* Throwing a Checked Exception
	* Like returning from a method, we can throw at any point.
* Throwing and Unchecked Exception
	* If exception is unchecked, we don’t have to mark the method, though we are welcome to.
* Wrapping and Rethrowing
	* Exceptions can be chained when one is a couse of another
	* e.g. catch (IOException io) {throw new PlayerLoadException(io);}
* Rethrowing Throwable or Exception
	* Read more about throwing errors in Lambda Expressions: https://4comprehension.com/sneakily-throwing-exceptions-in-lambda-expressions-in-java/
* Inheritance
	* When we mark methods with a throws keyword, it impacts how subclasses can override our method.
	* Subclasses can throw fewer checked exceptions than their superclass, but not more.
## Anti-Patterns
* Swallowing Exceptions
	* catch block which doesn't hand exception and don't rethrow it is called "swallowing exception"
	* it blocks other code from handling exception
* Using return in a finally Block
	* Another way to swallow exceptions is to return from the finally block. This is bad because, by returning abruptly, the JVM will drop the exception, even if it was thrown from by our code
* Using throw in a finally Block
	* Similar to using return in a finally block, the exception thrown in a finally block will take precedence over the exception that arises in the catch block.
		* This will “erase” the original exception from the try block, and we lose all of that valuable information
* Using throw as a goto
	* Exceptions are for error handling, not flow control of program
## Common Exceptions and Errors
* Checked Exceptions
	* IOException 
* Runtime Exceptions
	* ArrayIndexOutOfBoundsException 
	* ClassCastException 
	* NullPointerException 
	* IllegalStateException
* Errors
	* StackOverflowError 
	* NoClassDefFoundError 
	* OutOfMemoryError 