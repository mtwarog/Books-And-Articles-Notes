# Class Diagrams in UML  
[Link](https://medium.com/@smagid_allThings/uml-class-diagrams-tutorial-step-by-step-520fd83b300b)  
## What is Class Diagram
* Drawing representing conceptual understanding of the OO system in design.
## Purpose of Class Diagram
* Planning and modelling the system before writing code
* Comparing different designs
* Blueprint (a design plan) for use during development
## Concepts used by UML
* Class Representation
	* Class is represented as a box with 3 vertical compartments:
		* Name of class e.g. BankAccount
		* Class Attributes (a.k.a fields) e.g. balance: Double = 0.0
		* Class Methods (signatures) e.g. deposit(amount : Double)
* Visibility of Class Members
	* Visibility is marked before attibute or class name e.g. +owner : String
	* "+" public
	* "-" private
	* "#" protected
	* "~" package
* Relationships
	* Association
		* Symbol: -------->
		* Definition: It joins two entirely separate enities. There are 4 types of association:
			* bi-directional
			* uni-directional
			* aggregation (includes composition aggregation)
			* reflexive
			* Type can be specified by multiplicity (one to one, one to many, many to many)
		* Implemntation: Through instance field holding reference to other entity
	* Inheritance
		* Symbol: -------|>
		* Definition: Indicates that one class is specialization of another class
	* Realization/ Implementation
		* Symbol: - - - - |>
		* Definition: Indicates that one model element is realization of another e.g. MovablePoint class may be implementation of Movable interface
	* Dependency
		* Symbol: - - - - > 
		* Type: Aggregation
			* Symbol: --------<>
			* Definition: unidirectional (a.k.a one way) association of one class to another. Corresponds to "has a" or "is par of" language constructs.
			* E.g. A wallet "has" money. But monay doesn't neccessarily have wallet.
		* Type: Composition
			* Symbol: like aggregation, but <> is filled inside
			* Definition: Restricted form of aggregation in which two entities are hightly dependant on each other and can't exists without each other (they have the same lifespan)
			* E.g. Human and Heart classes
	* Multiplicity
		* After specyfing association relationship with arrows you can declare cardinality between associated entities.
