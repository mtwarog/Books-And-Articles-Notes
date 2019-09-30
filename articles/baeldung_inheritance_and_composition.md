# Inheritance and Composition in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-inheritance-composition)  
**Purpose**: Spotting the differences between Inheritance and Composition. Both are types of relationships.  
## Inheritance Basics
* When to use:
	* "If subtypes fulfill the “is-a” condition and mainly provide additive functionality further down the classes hierarchy, then inheritance is the way to go."
	* Method overriding is allowed as long as the overridden methods preserve the base type/subtype substitutability promoted by the Liskov Substitution Principle.
	* Additionally, we should keep in mind that the subtypes inherit the base type’s API, which is some cases may be overkill or merely undesirable.
	* In any other case we should use composition
## Inheritance in Design Patterns
* Layer Supertype Pattern
	* "use inheritance to move common code to a base class (the supertype), on a per-layer basis"
* Template Method Pattern
	* "use a base class to define the invariant parts of an algorithm, and then implement the variant parts in the subclasses"
## Composition Basics
* Composition allows us to model objects that are made up of other objects, thus defining a “has-a” relationship between them.
* Composition vs Association
	* The composition is the strongest form of association, which means that the object(s) that compose or are contained by one object are destroyed too when that object is destroyed.
* When to use:
	* "In every scenario where it’s possible to establish a semantically correct “has-a” relationship between a given class and others, the composition is the right choice to make."
* Aggregation vs Composition:
	* "the containing Computer object has ownership of the contained objects if and only if the objects can’t be reused within another Computer object. If they can, we’d be using aggregation, rather than composition, where ownership isn’t implied."
* When using composition prefer DI over rigid definition in fields
	* e.g. Computer(Memory memory) instead of Computer() {private Memory memory = new Memory();}