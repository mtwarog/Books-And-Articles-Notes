# Wrapper Classes in Java  
(part of Baeldung "Back to Basics")  
[Linkt to article](https://www.baeldung.com/java-wrapper-classes)  
**Purpose**: Generic classes (e.g. Collections) only work with objects and don’t support primitives. To be able to use primitives as types there is need to convert them to reference data types.  
* Wrapper classes are objects encapsulating primitive Java types
* They are all defined in java.lang package (so we don’t need to import them manually)
## Primitive to Wrapper Class
* we can either use constructor or static factory methods to convert a primitive value to an object 
* e.g. Integer object = new Integer(1); or Integer anotherObject = Integer.valueOf(1);
## Autoboxing and Unboxing
* Java 5 introduced autoboxing
* we shouldn’t use autoboxing e.g. inside a loop
* if we write a method that accepts a primitive value or wrapper object, we can still pass both values to them
	* Java will take care of passing the right type e.g. primitive or wrapper depending upon context.