# Java 9 Modules vs general module concept  
* In general module is a unit of organisation in which internal details are hidden, and that communicates with other modules via agreed contract. 
	* method can be module as it has hidden internals and contract (parameters and return value)
	* class can also be a module 
	* etc.
* Java 9 Module is a DEPLOYABLE module
* Java does have a deployable artifact called a JAR file, but these are not modules because they have no encapsulation or contract: at runtime JAR files disappear, all merging together into a single "classpath".
* OSGi addressed the lack of deployable modules in 1998 with the concept of a "bundle". These are physically JAR files and they contain packages, but OSGi defines additional metadata along with a runtime system to support encapsulation and contracts at that level.	
* Good Stack answer: https://softwareengineering.stackexchange.com/a/313545/338321
	* What's missing in core Java (pre-9) is a deployable module.
	* Java 9 addresses the lack of deployable modules in a similar way to OSGi. Arguably this was completely unnecessary because OSGi exists and works, but that's a whole different discussion
	* Unfortunately Java 9 muddies the waters by naming the new module concept just a "module". This does not mean that methods, classes and packages stop being modules! A J9 "module" is just another instantiation of the module concept. Like OSGi bundles, J9 modules are made out of packages and they are physical artifacts (usually JAR files again) that can be copied around. The runtime system understands and reifies them.