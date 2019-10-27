# Raw Types in Java  
* A raw type is the name of a generic class or interface without any type arguments
* For example, given gneric Box class: public class Box<T>. 
	* To create a parametrized type of Box<T>, you supply an actual type argument for the formal type parameter T: Box<Integer> intBox = new Box<>();
	* If the actual type argument is omitted, you create a raw type of Box<T>: Box rawBox = new Box();
	* However, a non-generic class or interface type is NOT a raw type.
* Raw types show up in legacy code because lots of API classes (such as the Collections classes) were not generic prior to JDK 5.0.
* When using raw types, you essentially get pre-generics behavior — a Box gives you Objects.
* The warning shows that raw types bypass generic type checks, deferring the catch of unsafe code to runtime. Therefore, you should avoid using raw types.