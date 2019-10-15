# JVM vs CLR - what are differences / similarities?  
[JavaCodeGeeks](https://www.javacodegeeks.com/2018/02/clr-vs-jvm-battle-net-java-extends-vm-level.html)  
## Similarities
* Are Virtual Machines
* Have Garbe Collection
* Employ stack-based operations
* runtime-level security
* methods for exception handling
## Differences
* CLR was designed to be language-neutral, JVM was designed to be Java-specific
* CLR was originally only Windows-compatible, JVM works with all major OSs
* CLR uses a JIT compiler, JVM uses a specialized JIT compiler called Java HotSpot
* CLR includes instructions for closures, coroutines and declaration/manipulation of pointers, the JVM does not
* JVM is compatible with more robust error resolution and production monitoring tools
## Virtual Machines
* System Virtual Machines
	* fully-functional machine emulation
* Process Virtual Machines
	* "specifically designed to run a process or program without being dependent on the platform environment."
	* CLR and JVM are process virtual machines
* Read more: [Stack](https://stackoverflow.com/a/480362/6708274)  