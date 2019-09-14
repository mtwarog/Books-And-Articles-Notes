# Java toString() method (part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-tostring)  
**Purpose**: To get string representation of object. Every object has toString() method (but not necessarly implementation of it)  
* Default Behavior
	* Object implementation of toString():
		* return getClass().getName()+"@"+Integer.toHexString(hashCode());
* Overriding Default Behavior
	* Generally, we aren’t interested in knowing the hashcode of an object, but rather the contents of our object’s attributes
* Primitive Types and Strings
	* We can simply concatenate primitive types and Strings: 
	* e.g. return "Customer [balance=" + balance + ", getFirstName()=" + getFirstName() + ", getLastName()=" + getLastName() + "]";
* Complex Java Objects
	* If object contains references to other objects, then those referenced objects should also implement toString() to be able to iclude it is toString() of main object
* Array of Objects
	* Use Arrays.toString(someObjectsArray) to call toString() on every object 
* Wrappers, Collections and StringBuffers
	* When an object is made up entirely of wrappers, collections, or StringBuffers, no custom toString() implementation is required because these objects have already overridden the toString() method with meaningful representations
	* e.g. Integer score; List<String> orders; StringBuffer fullname;
* toString() generation
	* In todays IDEs toString method can be easily generated e.g. in Intellij
	* Kotlin autogenerates toString with data keyword
	* Lombok @ToString annotation is doing the same