# Final keyword in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java*final)  
**Purpose**: To set limitations of extensibility of class inheritance.  
## Final classes
* Classes marked as final can’t be extended
* Example from standard library: String class
	* why String is final?
	* because substituting String with it's subclasses would lead to unpredictable behavior, which would pose a problem for e.g. security of code
* The final keyword in a class declaration doesn’t mean that the objects of this class are immutable
* Con: Making class final means no programmer can make improvements
## Final methods
* Methods marked as final cannot be overridden
* Example from standard library: Thread class isAlive() method
	* this method is native and is specific to OS and hardware
## Final variables
* Variables marked as final can’t be reassigned.
* any final field must be initialized before the constructor completes
* Final Arguments
	* A final argument can’t be changed inside a method
	* e.g. public void methodWithFinalArguments(final int x) {...}