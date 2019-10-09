# Java Packages  
[Link to article](https://www.baeldung.com/java-packages)  
**Purpose**: "we use packages to group related classes, interfaces and sub-packages."  
* Benefits of packages:
	* Making related types easier to find – packages usually contain types that are logically related
	* Avoiding naming conflicts – a package will help us to uniquely identify a class; for example, we could have a com.baeldung.Application, as well as com.example.Application classes
	* Controlling access - we can control visibility and access to types by combining packages and access modifiers
* Creating Package
	* To create a package, we have to use the package statement by adding it as the very first line of code in a file.
	* It’s highly recommended to add each new type in a package.
	* Naming Convention
		* names in all lower case
		* package names are period-delimited
		* names are also determined by the company or organization that creates them 
		* To determine the package name based on an organization, we’ll typically start by reversing the company URL. (e.g. com.mactwa.Type)
	* Directory Structure
		* Packages in Java correspond with a directory structure.
		* Each package and subpackage has its own directory. So, for the package com.baeldung.packages, we should have a directory structure of com -> baeldung -> packages.
* Using Package Members
	* Imports
		* We can import a single type from a package or use an asterisk to import all of the types in a package.
	* Fully Qualified Name
		* When we run into naming conflicts, we need to use a fully qualified class name for at least one of the classes.
			* e.g. private List<com.baeldung.packages.domain.TodoItem> todoItems;
* Compiling with javac tool
	* Dependencies must be compiled first
	* For types that reference types in other packages, we should use the -classpath flag to tell the javac command where to find the other compiled classes.
## Read more: 
[Read more](https://docs.oracle.com/javase/specs/jls/se9/html/jls-7.html)  
* Programs are organized as sets of packages. The members of a package are class and interface types, which are declared in compilation units of the package, and subpackages, which may contain compilation units and subpackages of their own.
* Each package has its own set of names for types, which helps to prevent name conflicts. The naming structure for packages is hierarchical.
* If a set of packages is sufficiently cohesive, then the packages may be grouped into a module. A module categorizes some or all of its packages as exported, which means their types may be accessed from code outside the module. If a package is not exported by a module, then only code inside the module may access its types.
* A  module controls how its packages use other modules (by specifying dependences) and controls how other modules use its packages (by specifying which of its packages are exported)
## Java Packages vs C# Namespaces
* Good Stack answer: https://stackoverflow.com/a/9249506/6708274 
* Packages are used to organize files or public types to avoid type conflicts. Package constructs can be mapped to a file system.
* Package cannot be nested. One source file can only have one package statement.
* Namespaces are used to organize programs, both as an "internal" organization system for a program, and as an "external" organization system.
* Okay, after the clarification: a Java package is similar to a C# namespace - except that it has an impact on accessibility, whereas in C# namespaces and accessibility are entirely orthogonal.
## Hierarchy of all Java Packages 
[Link](https://docs.oracle.com/javase/7/docs/api/overview-tree.html)  
* read more: check if I understand every packages (what is does only)