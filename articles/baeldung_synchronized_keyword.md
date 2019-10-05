# Synchronised keyword in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-synchronized)  
**Purpose**: "in a multi-threaded environment, a race condition occurs when two or more threads attempt to update mutable shared data at the same time.   
* Java offers a mechanism to avoid race conditions by synchronizing thread access to shared data."
* A piece of logic marked with synchronized becomes a synchronized block, allowing only one thread to execute at any given time.
* synchronised keyword may be applied to:
	* instance methods
		* Instance methods are synchronized over the instance of the class owning the method. Which means only one thread per instance of the class can execute this method.
	* static methods
		* only one Class object exists per JVM per class, only one thread can execute inside a static synchronized method per class, irrespective of the number of instances it has.
	* code blocks
		* Sometimes we do not want to synchronize the entire method but only some instructions within it.
* When we use a synchronized block, internally Java uses a monitor also known as monitor lock or intrinsic lock, to provide synchronization. 
	* These monitors are bound to an object, thus all synchronized blocks of the same object can have only one thread executing them at the same time.
* e.g. public synchronized void synchronisedCalculate() {setSum(getSum() + 1);}