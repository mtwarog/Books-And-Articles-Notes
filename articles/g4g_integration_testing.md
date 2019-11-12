# Integration testing 
(part of Software Engineering on Geeks4Geeks, Software Testing and Debugging)  
[Link to article](https://www.geeksforgeeks.org/software-engineering-integration-testing/)  
**Definition**: Integration testing definition: process of testing the interface between two software units or module. It’s focus on determining the correctness of the interface. The purpose of the integration testing is to expose faults in the interaction between integrated units. Once all the modules have been unit tested, integration testing is performed.  
## Approaches to integration testing
### Big-Bang Integration testing
* It is the simplest integration testing approach, where all the modules are combining and verifying the functionality after the completion of individual module testing. In simple words, all the modules of the system are simply put together and tested. This approach is practicable only for very small systems.
* Advatages: It is convenient for small systems.
* Disadvatages: There will be quite a lot of delay because you would have to wait for all the modules to be integrated. High risk critical modules are not isolated and tested on priority since all modules are tested at once.
### Bottom-Up Integration testing
* In bottom-up testing, each module at lower levels is tested with higher modules until all modules are tested. The primary purpose of this integration testing is, each subsystem is to test the interfaces among various modules making up the subsystem. This integration testing uses test drivers to drive and pass appropriate data to the lower level modules.
* Advatages: No Stubs are required, several disjoint subsystems can be tested simultaneously
* Disavatages: Driver modules must be produced. The complexity that occurs when the system is made up of a large number of small subsystem.
### Top-down Integration testing
* Top-down integration testing technique used in order to simulate the behaviour of the lower-level modules that are not yet integrated.In this integration testing, testing takes place from top to bottom. 
* First high-level modules are tested and then low-level modules
* Advantages: Few or no drivers needed. 
* Disadvantages: Needs many Stubs. Modules at lower level are tested inadequately.
### Mixed Integration testing a.k.a sandwitched integration testing
* A mixed integration testing follows a combination of top down and bottom-up testing approaches. In top-down approach, testing can start only after the top-level module have been coded and unit tested. In bottom-up approach, testing can start only after the bottom level modules are ready. This sandwich or mixed approach overcomes this shortcoming of the top-down and bottom-up approaches.
* Advantages: Useful for very large projects having multiple subprojects. Overcomes shortcomings of top-down and bottom-up approaches
* Disadvatages: Require very high cost because one part has Top-down approach while another part has bottom-up approach.