# Switch statement in Java 
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-switch)  
**Purpose**: To have control flow utility with multiple branches to choose from.  
The switch statement allows us to replace several nested if-else constructs and thus improve the readability of our code.
* Switch was upgraded in Java 5 and Java 7
* Switch expression (not statement) will be likely introduced in Java 12
* Break statement
	* Simply put, the break statement is used to exit a switch statement
	* If we forget to write a break, the blocks underneath will be executed.
	* Omit break when we want the same code executed for several case statements
* A switch works only with four primitives and their wrappers, as well as with the enum type and the String class:
	* byte and Byte (wrapper classes since Java 5)
	* short and Short
	* int and Integer
	* char and Character
	* enum (since Java 5) 
	* String (since Java 7)
* Con: We can’t pass the null value as an argument to a switch statement
* Case Values must be Compile-Time Constants 
	* meaning it must be either literal value or final variable
* Switch operator uses the equals() method under the hood to compare Strings
* When to use?
	* The switch statement is a good candidate for cases when we have a limited number of options in a pre-defined set (eg: days of the week). 
		* Otherwise, we’d have to modify the code each time a new value is added or removed, which may not be feasible. 
* Java 12 new Switch:
e.g.    
	var value = switch(month) {
		case JAN, JUN, JUL -> 3;
		case FEB, SEP, OCT, NOV, DEC -> 1;
		case MAR, MAY, APR, AUG -> 2;
	};