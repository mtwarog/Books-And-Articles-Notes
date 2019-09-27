# Why Strings are Immutable in Java?  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-string-immutable)  
* Benefits of Immutability:
	* Caching
	* Security
	* Easy reuse without replication
*Immutable object definition*: "object whose internal state remains constant after it has been entirely created"  
## Why is String Immutable?
* Short Answer
	* Strings are immutable precisely so that their references can be treated as a normal variable and one can pass them around, between methods and across threads, without worrying about whether the actual String object it’s pointing to will change.
## String Pool
* Java String Pool is the special memory region where Strings are stored by the JVM. 
	* Since Strings are immutable in Java, the JVM optimizes the amount of memory allocated for them by storing only one copy of each literal String in the pool. 
	* This process is called interning.
* Read more: https://www.baeldung.com/java-string-pool
## Security
* The String is widely used in Java applications to store sensitive pieces of information like usernames, passwords, connection URLs, network connections, etc. 
	* It’s also used extensively by JVM class loaders while loading classes.
* If Strings were mutable, then by the time we execute the update, we can’t be sure that the String we received, even after performing security checks, would be safe.
	* e.g. different thread could change this string in meantime
## Synchronisation
* Being immutable automatically makes the String thread safe since they won’t be changed when accessed from multiple threads.
* immutable objects, in general, can be shared across multiple threads running simultaneously.
## Hashcode Cashing
* the hashCode() method is overridden in String class to facilitate caching, such that the hash is calculated and cached during the first hashCode() call and the same value is returned ever since.
* This, in turn, improves the performance of collections that uses hash implementations when operated with String objects.
## Performance
* Since String is the most widely used data structure, improving the performance of String have a considerable effect on improving the performance of the whole application in general.