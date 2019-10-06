# Java try-with-resources  
(part of Baeldung "Back to Basics")  
Starting point: https://www.baeldung.com/java-try-with-resources  
* Introduced in Java 7  
**Purpose**: allows us to declare resources to be used in a try block with the assurance that the resources will be closed when after execution of that block.  
* The resources declared must implement the AutoCloseable interface.
* Simply put, to be auto-closed, a resource must be both declared and initialized inside the try, as shown below:
	* try (PrintWriter writer = new PrintWriter(new File("test.txt"))) {writer.println("Hello World");}