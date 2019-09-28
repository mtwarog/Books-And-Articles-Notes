# Finalize method in Java  
(part of Baeldung "Back to Basics")  
[Link to article](https://www.baeldung.com/java-finalize)  
**IMPORTANT**: One critical point to notice is that finalize has been deprecated starting with Java 9 – and will eventually be removed.  
**Purpose**: It is called before the garbage collection for a particular object. It was introduced to finilize existence (e.g. connections to other objects) of object.  
* The finalize() method is called the finalizer. It is provided by root Object class.  
## Using Finalizers
* Finalizers get invoked when JVM figures out that this particular instance should be garbage collected. Such a finalizer may perform any operations, including bringing the object back to life.
* The main purpose of a finalizer is, however, to release resources used by objects before they’re removed from the memory. A finalizer can work as the primary mechanism for clean-up operations, or as a safety net when other methods fail.
* the time at which the garbage collector calls finalizers is dependent on the JVM’s implementation and the system’s conditions, which are out of our control.
## Avoiding Finalizers
* The first noticeable issue associated with finalizers is the lack of promptness. We cannot know when a finalizer is executed since garbage collection may occur anytime.
* Finalizers also have an impact on the program’s portability. Since the garbage collection algorithm is JVM implementation dependent, a program may run very well on one system while behaving differently at runtime on another.
* JVM must perform much more operations when constructing and destroying objects containing a non-empty finalizer
* If a finalizer throws an exception, the finalization process is canceled, and the exception is ignored, leaving the object in a corrupted state without any notification