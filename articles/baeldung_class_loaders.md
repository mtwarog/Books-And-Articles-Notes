# Class Loaders: ClassNotFoundException vs NoClassDefFoundError  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-classnotfoundexception-and-noclassdeffounderror)  
**Purpose**: Both occurs when the JVM can not find a requested class on the classpath. There are some differences between them.  
**Short answer**: Java runtime throws ClassNotFoundException while trying to load a class at runtime only and the name was provided during runtime. In the case of NoClassDefFoundError, the class was present at compile time, but Java runtime could not find it in Java classpath during runtime.  
## ClassNotFoundException
* is a checked exception which occurs when an application tries to load a class through its fully-qualified name and can not find its definition on the classpath.
* occurs in reflections when using Class.forName(), ClassLoader.loadClass() or ClassLoader.findSystemClass()
## NoClassDefFoundError
* is a fatal error. It occurs when JVM can not find the definition of the class while trying to:
	* Instantiate a class by using new keyword
	* Load a class with a method call
* The error occurs when a compiler could successfully compile the class, but Java runtime could not locate the class file. It usually happens when there is an exception while executing a static block or initializing static fields of the class, so class initialization fails.