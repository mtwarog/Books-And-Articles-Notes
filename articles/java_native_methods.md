# Java Native Methods  
* Good Stack answer: [Stack](https://stackoverflow.com/a/29311166/6708274)  
* Allows to:
	* call a compiled dynamically loaded library (here written in C) with arbitrary assembly code from Java
	* get result back to Java
* Use cases:
	* write faster code on a critical section with better CPU assembly instructions (not CPU portable)
	* make direct system calls (not OS portable)
* Native keyword and methods: https://www.baeldung.com/java-native
	* native keyword - non-access modifier that is used to access methods implemented in a language other than Java like C/C++.
* Java JNI == Java Native Interface
* Drawback
	* Compiled native method is often architecture-dependant, which is against WORA principle of Java
* Read more: https://www.baeldung.com/jni