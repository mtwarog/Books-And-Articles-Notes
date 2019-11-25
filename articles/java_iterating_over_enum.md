# Iterating over enum in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-enum-iteration)  
**Purpose**: To iterate through all enumerated values (e.g. for lookup or counting  
* Enum is a datatype that helps us assign a predefined set of constants to a variable
* Enums do not have methods for iteration like forEach() or iterator(). Instead, we can use the array of the Enum values returned by the values() method
## Iterating using
* for loop
	* e.g. for (DaysOfWeekEnum day : DaysOfWeekEnum.values()) { System.out.println(day); }
* Stream
	* using Stream.of() or Arrays.stream()
* forEach()
	* forEach() is an element of Iterable interface in Java 8. To use it we need to first convert Enum to suitable collection. We can use Arrays.asList().
* EnumSet
	* EnumSet is specialized set implementation that we can use with Enum types.
	* e.g. EnumSet.allOf(DaysOfWeekEnum.class).forEach(day -> System.out.println(day));
* ArrayList of Enum Values
	* We can also add values of an Enum to a List. This allows us to manipulate the List like any other