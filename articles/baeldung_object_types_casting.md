# Object Type Casting in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-type-casting)  
* read also primitive types casting: [Primitive Types Casting](https://www.baeldung.com/java-primitive-conversions)  
**Purpose**: To change interface (list of available members) of object. Upcasting narrow, and downcasting broadens list of available members.  
* "A reference is like a remote control to an object. The remote control has more or fewer buttons depending on its type, and the object itself is stored in a heap. 
	* When we do casting, we change the type of the remote control but don’t change the object itself."
## Upcasting
* Casting from a subclass to a superclass is called upcasting
* Upcasting is safe so it can be implicit e.g.
	* Cat cat = new Cat();
	* Animal animal = cat; // implicit cast is done: (Animal) cat;
* Polymorphism
	* Thanks to upcasting, we can take advantage of polymorphism.
	* Upcasting is modifying interface, not the implementation of methods.
	* Animal cat = new Cat(); cat.voice() will still print "Mew mew" (not Animal implementation of voice(), but Cat implementation)
## Downcasting
* Casting from superclass to subclass
* () - cast operator e.g. (Cat) animal; 
* instanceof operator - can be used to check if the object belongs to the specific type before downcasting (check actual object, not a reference)
* ClassCastException - thrown at runtime if casted object is not in inheritance tree of type we are casting to
## Cast() method
* there is an alternative method of casting (to cast operator) - Cast() method e.g. Cat.class.cast(animal) // casting animal to Cat type
* similarly: Cat.class.isInstance(animal) is an alternative to instanceof