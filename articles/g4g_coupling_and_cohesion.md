# Coupling and Cohesion 
(part of Software Engineering on Geeks4Geeks, Software Development Models & Architecture)  
[Link to article](https://www.geeksforgeeks.org/software-engineering-coupling-and-cohesion/)
## Purpose of Design Phase in SDLC  
* The purpose of Design phase in the Software Development Life Cycle is to produce a solution to a problem given in the SRS(Software Requirement Specification) document. 
* The output of the design phase is Sofware Design Document (SDD).
## Conceptual Design of system
* Written in simple language, customer understandable
* Describes the functionality of the system.
* It is independent of implementation.
* Linked with requirement document.
## Technical Design of system
* Hardware component and design.
* Functionality and hierarchy of software component.
* Software and Network architectures
* Flow of data, IO etc.
## Modularization
* Modularization is the process of dividing a software system into multiple independent modules where each module works independently. 
* Advantages:
	* Easy to understand
	* Easier maintenance
	* Reusability of modules e.g. in different application
## Coupling
* Definition: Coupling is the measure of the degree of interdependence between the modules. Good software will have low coupling.
* Types of Coupling
	* Data Coupling* - If the dependency between the modules is based on the fact that they communicate by passing only data, then the modules are said to be data coupled
	* Stamp Coupling* - In stamp coupling, the complete data structure is passed from one module to another module
	* Control Coupling* - If the modules communicate by passing control information, then they are said to be control coupled. It can be bad if parameters indicate completely different behavior and good if parameters allow factoring and reuse of functionality. 
		* Example* sort function that takes comparison function as an argument.
	* External Coupling* - In external coupling, the modules depend on other modules, external to the software being developed or to a particular type of hardware. Ex* protocol, external file, device format, etc.
	* Common Coupling* - The modules have shared data such as global data structures.The changes in global data mean tracing back to all modules which access that data to evaluate the effect of the change.
		* It has got disadvantages like difficulty in reusing modules, reduced ability to control data accesses and reduced maintainability.
	* Content Coupling* - In a content coupling, one module can modify the data of another module or control flow is passed from one module to the other module. 
		* This is the worst form of coupling and should be avoided.
## Cohesion
* Definition: Cohesion is a measure of the degree to which the elements of the module are functionally related. 
	* It is the degree to which all elements directed towards performing a single task are contained in the component. 
	* Basically, cohesion is the internal glue that keeps the module together. 
	* A good software design will have high cohesion.
* Types of Cohesion 
	* Functional Cohesion* -  Every essential element for a single computation is contained in the component. 
		* A functional cohesion performs the task and functions. It is an ideal situation.
	* Sequential Cohesion* - An element outputs some data that becomes the input for other element, i.e., data flow between the parts. It occurs naturally in functional programming languages.
	* Communicational Cohesion* -  Two elements operate on the same input data or contribute towards the same output data. 
		* Example* - update record int the database and send it to the printer.
	* Procedural Cohesion* - Elements of procedural cohesion ensure the order of execution. Actions are still weakly connected and unlikely to be reusable. 
		* Example* - calculate student GPA, print student record, calculate cumulative GPA, print cumulative GPA.
	* Temporal Cohesion* - The elements are related by their timing involved. A module connected with temporal cohesion all the tasks must be executed in the same time-span. This cohesion contains the code for initializing all the parts of the system. Lots of different activities occur, all at init time.
	* Logical Cohesion* -  The elements are logically related and not functionally. 
		* Example* - A component reads inputs from tape, disk, and network. All the code for these functions is in the same component. Operations are related, but the functions are significantly different.
	* Coincidental Cohesion* - The elements are not related(unrelated). The elements have no conceptual relationship other than location in source code. It is accidental and the worst form of cohesion. 
		* Example* - print next line and reverse the characters of a string in a single component.