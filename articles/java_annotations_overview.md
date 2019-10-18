# Overview of Java Annotations  
* Annotation - Java types that are preceded by an "@" symbol.
* Available since Java 5  
[Built-in annotations](https://www.baeldung.com/java-default-annotations)  
* an annotation assigns extra metadata to the source code it’s bound to
* Using this metadata one can:
	* Inform the compiler about warnings and errors
	* Manipulate source code at compilation time
	* Modify or examine behavior at runtime
## List of built-in annotations
* @Override - signals that annotated method overrides of inherited method
* @SuppressWarnings - indicates that some compilation warning should be ignored
* @Deprecated - used to mark API as not intended for use anymore
* @SafeVarargs - alsu supresses errors related to varargs
* @FunctionalInterface - Prevents future programmer error (this interface MUST have only one abstract method. Can have default methods though)
## Meta-annotations 
Annotations which can be applied to other annotations  
* @Target - determine the target elements of a custom annotation
* @Retention - determine where in our program lifecycle annotation applies (there are 3 retention policies)
	* SOURCE – visible by neither the compiler nor the runtime (default)
	* CLASS – visible by the compiler
	* RUNTIME – visible by the compiler and the runtime
* @Inherited - make annotation propagate from an annotated class it its subclasses
* @Documented - by default Java doesn't document usage of annotations in Javadocs. It can be changed by this annotation
* @Repeatable - can make given annotation apply to element multiple times
## Misc	
* Annotations doesn't have any equivalent in Cpp
	* [Stack](https://stackoverflow.com/a/14821945/6708274)  
	* "use of annotations is to have tools that intervenes at compile time to inject some code or to do checks. The tool to do this kind of stuff in C++ is the preprocessor."
* Framework-specific annotations
	* "Spring and Hibernate are great examples of frameworks that rely heavily on annotations to enable various design techniques."