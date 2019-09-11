# User Interface Design   
(part of Software Engineering on Geeks4Geeks, Software Development Models & Architecture)  
[Link to article](https://www.geeksforgeeks.org/software-engineering-user-interface-design/)  
## Characteristics of good UI:
* Attractive
* Simple to use
* Responsive in short time
* Clear to understand
* Consistent on all interface screens
## Types of UI:
* CLI: Command Line Interface
	*  Command Line Interface provides a command prompt, where the user types the command and feeds to the system. The user needs to remember the syntax of the command and its use.
* GUI: Graphical User Interface
	* Graphical User Interface provides the simple interactive interface to interact with the system. GUI can be a combination of both hardware and software. Using GUI, user interprets the software.
## UI Design Process:
* User, task, environmental analysis, and modeling
	* Profile of users is investigated and based on this profile requirements are defined
* Interface Design
	* The goal of this phase is to define the set of interface objects and actions i.e. Control mechanisms that enable the user to perform desired tasks.
	* Specify the action sequence of tasks and subtasks, also called a user scenario.
	*  Design issues such as response time, command and action structure, error handling, and help facilities are considered as the design model is refined.
* Interface construction and implementation
	* The implementation activity begins with the creation of prototype (model) that enables usage scenarios to be evaluated.
* Interface Validation
	* This phase focuses on testing the interface. The interface should be in such a way that it should be able to perform tasks correctly and it should be able to handle a variety of tasks. It should achieve all the user’s requirements. 
## Golden Rules of UI design (stated by Theo Mandel):
* Place user in control
	* Define the interaction modes in such a way that does not force the user into unnecessary or undesired actions: The user should be able to easily enter and exit the mode with little or no effort.
	* Provide for flexible interaction: Different people will use different interaction mechanisms, some might use keyboard commands, some might use mouse, some might use touch screen, etc, Hence all interaction mechanisms should be provided.
	* Hide technical internals from casual users
	* Allow user interaction to be interruptable and undoable
	* Design for direct interaction with objects that appear on screen
* Reduce the user's memory load
	* Reduce demand on short-term memory: When users are involved in some complex tasks the demand on short-term memory is significant.
	* Establish meaningful defaults: Always initial set of defaults should be provided to the average user
	* Define shortcuts that are intuitive
	* The visual layout of the interface should be based on a real-world metaphor: Anything you represent on a screen if it is a metaphor for real-world entity then users would easily understand.
* Make the interface consistent
	* Allow the user to put the current task into a meaningful context
	* Maintain consistency across a family of applications
	* If past interactive models have created user expectations do not make changes unless there is a compelling reason