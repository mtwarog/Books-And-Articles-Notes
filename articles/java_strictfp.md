# Strictfp keyword in Java
[Link to article](https://www.geeksforgeeks.org/strictfp-keyword-java/)  
* means STRICT Floating-Point operations
* keyword in java used for restricting floating-point calculations and ensuring same result on every platform while performing operations in the floating-point variable
* By default, Floating point calculations are platform dependent i.e. different output(floating-point values) is achieved when a class file is run on different platforms(16/32/64 bit processors)
* To solve this type of issue, strictfp keyword was introduced in JDK 1.2 version by following IEEE 754 standards for floating-point calculations
* strictfp modifier is used with classes, interfaces and methods only
* e.g. strictfp class Test {// all concrete methods here are implicitly strictfp.}