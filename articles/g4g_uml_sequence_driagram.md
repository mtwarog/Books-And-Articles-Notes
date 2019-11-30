# Sequence Diagram (a.k.a Event Diagrams or Event Scenarios) in UML  
[Link](https://www.geeksforgeeks.org/unified-modeling-language-uml-sequence-diagrams/)  
**Definition**: Drawing which depicts interaction between objects in order in which these interactions take place  
**Purpose**: Used by businessman and software developers to understand requirements for new or existing systems  
* Sequence diagram is the most commonly used interaction diagram
* Interaction Diagram definition: An interaction diagram is used to show the interactive behavior of a system. 
	* Since visualizing the interactions in a system can be a cumbersome task, we use different types of interaction diagrams to capture various features and aspects of interaction in a system.
## Sequence Diagrams notations:
* Actors 
	* Represents a type of role where it interacts with the system and its objects.
	* Actor is always outside the scope of the system we aim to model using the UML diagram 
	* We use actors to depict various roles including human users and other external subjects
	* Pictured as a "stick person"
* Lifelines 
	* A named element which depicts an individual participant in a sequence diagram
	* Each instance in sequence diagram is represented by a lifeline
	* Represented by rectangle with vertical dashed line
	* Agent vs Lifeline: lifeline is always internal for the system, where actior is always external.
* Messages 
	* Communication between objects is depicted using messages
	* The messages appear in a sequential order on the lifeline. 
	* We represent messages using arrows.
	* Categories of messages:
		* Synchronous messages
			* A synchronous message waits for a reply before the interaction can move forward. The sender waits until the receiver has completed the processing of the message.
			* We use solid arrow head to represent a synchronous message
		* Asynchronous messages
			* An asynchronous message does not wait for a reply from the receiver. The interaction moves forward irrespective of the receiver processing the previous message or not.
			* We use a lined arrow head to represent an asynchronous message.
		* Create message
			* We use a Create message to instantiate a new object in the sequence diagram
			* It creates new lifeline in sequence diagram
			* It is represented with a dotted arrow and create word labelled on it to specify that it is the create Message symbol.
		* Delete Message
			* We use a Delete Message to delete an object. When an object is deallocated memory or is destroyed within the system we use the Delete Message symbol.
			* It is represented by an arrow terminating with a x.
		* Self message
			* Certain scenarios might arise where the object needs to send a message to itself.
			* Such messages are called Self Messages and are represented with a U shaped arrow.
		* Reply message
			* Reply messages are used to show the message being sent from the receiver to the sender. 
			* We represent a return/reply message using an open arrowhead with a dotted line.
		* Found message
			* A Found message is used to represent a scenario where an unknown source sends the message. 
			* It is represented using an arrow directed towards a lifeline from an end point.
			* E.g. it is a hardware failure message, but the source of failure is not known
		* Lost message
			* A Lost message is used to represent a scenario where the recipient is not known to the system. 
			* It is represented using an arrow directed towards an end point from a lifeline.
* Guards 
	* Used to model conditions. They are used when we need to restict the flow of message. Guards let messaging only if certain conditions are met (defined in guard)
	* Guards play an important role in letting software developers know the constraints attached to a system or a particular process.
	* e.g. "In order to be able to withdraw cash, having a balance greater than zero is a condition that must be met"
## Example:
* A sequence diagram for an emotion based music player:
* Actors: User
* Lifelines: Device, Database
* Messages: 
	* 1. User -> Device: Open Application
	* 2. Device -> Device: Access Webcam
	* 3. Device -> User: Get Photo
	* 4. User -> Device: Detect Face
	* 5. Device -> Database: Retrieve Mood
	* 6. Database -> Device: Mood
	* ... 
## Uses of sequence diagram:
* Used to model and visualise the logic behind a sophisticated function, operation or procedure.
* They are also used to show details of UML use case diagrams.
* Used to understand the detailed functionality of current or future systems.
* Visualise how messages and tasks move between objects or components in a system.
**Read more**: [Link](https://www.agilemodeling.com/artifacts/sequenceDiagram.htm)  
