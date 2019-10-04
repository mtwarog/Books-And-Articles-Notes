# Volatile keyword in Java  
(part of Baeldung "Back to Basics")  
**Purpose**: in Java, threads have their own memory, spearated from main memory of program. Usually operation is performed on a variable in thread memory and then it is copied for other threads to the main memory.   
* Simply put, the volatile keyword marks a variable to always go to main memory, for both reads and writes, in the case of multiple threads accessing it.  
## Volatile and Thread Synchronisation
* For all multithreaded applications we need to provide:
	* Mutual Exclusion - only one thread executes a critical section at a time
	* Visibility - changes made by one thread to the shared data, are visible to other threads to maintain a data consistency
* Synchronized methods and blocks provide both of the above properties, at the cost of performance of the application.
* Volatile is quite a useful primitive because it can help ensure the visibility aspect of the data change, without, of course, providing the mutual exclusion
## "Happens-Before" Guarantee
* From Java 5 volatile also provides additional capabilities for non-volatile variables
* read more about that