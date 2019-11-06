# Transient keyword in Java  
[Link to article](https://www.geeksforgeeks.org/transient-keyword-java/)  
**Purpose**: Transient keyword marks fields which should be ommited during serialization  
* is a variables modifier used in serialization. At the time of serialization, if we don’t want to save value of a particular variable in a file, then we use transient keyword.
* When JVM comes across transient keyword, it ignores original value of the variable and save default value of that variable data type.
* Use Cases:
	* transient keyword plays an important role to meet security constraints. There are various real-life examples where we don’t want to save private data in file.
	* Another use of transient keyword is not to serialize the variable whose value can be calculated/derived using other serialized objects
* transient and static : Since static fields are not part of state of the object, there is no use/impact of using transient keyword with static variables
* transient and final : final variables are directly serialized by their values, so there is no use/impact of declaring final variable as transient.