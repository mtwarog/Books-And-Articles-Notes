# Primitive Type Casting in Java  
[Link to article](https://www.baeldung.com/java-primitive-conversions)  
**Purpose**: Change value to support bigger / smaller values (modify amount of memory assigned to variable)  
* There are 8 primitive data types: byte, short (16 bit, signed), char (16 bit, unassigned, that it can represent Unicode characters), int, long, float, double, boolean (true or false only)
* Widening Primitive Conversion
	* Is safe (doesn't loose any information), therefor it can be implicit e.g. int myInt = 127; long myLong = myInt;
* Narrowing Primitive Conversion
	* Sometimes we need to fit a value that is larger than the type used in the variable declaration. This may result in information loss since some bytes will have to be discarded.
	* Not safe, so must be explicit e.g. byte myByte = (byte) myInt;
* Special case: Widening and Narrowing Primitive Conversion
	* This situation happens in a very specific case when we want to convert from a byte to a char. The first conversion is the widening of the byte to int and then from the int it is narrowed down to char.
	* e.g. byte myLargeValueByte = (byte) 130;   //0b10000010 -126 // The binary representation of 130 is the same for -126, the difference is the interpretation of the signal bit
* Boxing / Unboxing Conversion
	* In Java, we have a Wrapper Class for each primitive type. 
	* Java 5 introduced auto-boxing and auto-unboxing e.g. Integer myIntegerReference = myInt; int myOtherInt = myIntegerReference; // without explicit wrapper instantiation
* String Conversion
	* All the primitive types may be converted to String through their Wrapper Classes, which override the toString() method
	* If we need to go back to a primitive type, we need to use a parse method defined by the corresponding Wrapper Class 
		* e.g. byte myNewByte = Byte.parseByte(myString)
* Numeric Promotions
	* To execute a binary operation, it is necessary that both operands are compatible in terms of size.
	* There is few simple rules that apply, but in general one of operands will be casted to: int, double, float or long 