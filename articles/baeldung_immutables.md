# Immutables in Java  
[Link to article](https://www.baeldung.com/java-immutable-object)  
**Definition**: "An immutable object is an object whose internal state remains constant after it has been entirely created."  
* API of such object give us read-only methods
* Variables are mutable by default, meaning we can change the value they hold.
* final keyword - Note that final only forbids us from changing the reference the variable holds, it doesn’t protect us from changing the internal state of the object
* If immutable object contains reference to other object it also must be immutable. This referenced object must guarantee immutability on it's own.
* Benefits
	* We can share immutable object safely among multiple threads
	* Immutable objects are side-effects free