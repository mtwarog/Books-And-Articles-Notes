# Rounding Decimal Numbers in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-round-decimal-number)  
**Purpose**: Precise calculations, presenting results in desired format  
## Decimal Numbers in Java
* In java there are two primitive types which allows to store decimal numbers: float and double
* both types should never be used for precise values, such as currencies
* For that, and also for rounding, we can use the BigDecimal class
## Formatting a Decimal Number
* If we just want to print a decimal number with n digits after decimal point, we can simply format the output String:
	* e.g. System.out.printf("Value with 3 digits after decimal point %.3f %n", PI);
* Also DecimalFormat class can be used:
	* e.g. DecimalFormat df = new DecimalFormat("###.###"); System.out.println(df.format(PI));
## Rounding Doubles with BigDecimal
* when constructing BigDecimal; we must always use BigDecimal(String) constructor. This prevents issues with representing inexact values.
* also Apache Commons Math library can be used:
	* e.g. Precision.round(PI, 3);
## Rounding Doubles with DoubleRounder (from decimal4j library)
* fast and garbage-free method for rounding doubles from 0 to 18 decimal points
## Math.round() method (not recommended)
* This method is not recommended as it’s truncating the value. In many cases values are rounded incorrectly